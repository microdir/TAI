# Reconhecimento de Gestos em Libras

## Introdução
   O relatório a seguir tem o objetivo de mostrar ao leitor um breve histórico do processo de desenvolvimento de um algorítimo, escrito pelos alunos João Marcos e Michel Rodrigo, que é capaz de reconhecer gestos em Libras (Linguagem Brasileira de Sinais).
   O projeto foi desenvolvido como atividade final da disciplina de Tópicos Avançados em Informática na Escola de Ciência e Tecnologia da UFRN, ministrada pelo professor Orivaldo Santana.
   É importante salientar que o objetivo foi cumprido (reconhecer os gestos), porém, não é algo simples o suficiente para ser concluído com tanta rapidez. Portanto, para iniciarmos o projeto, o algorítimo reconhece atualmente apenas gestos gestos em libras que representam as vogais do nosso alfabeto, mas com um pouco de refino e um banco de dados mais robusto tem grande potencial para o reconhecimento de todo o alfabeto.

## Metodologia
   O modelo de Machine Learning utilizado no processo foi o da rede SOM (Self-Organized-Maps), que, de cordo com PINHEIRO (2019) “é uma rede neural de 2 camadas que aceita padrões de N-dimensões como entrada e os mapeia para um conjunto de neurônios de saída, o qual representa o espaço dos dados a serem agrupados”.
   A ideia principal desse modelo é fazer com que dados semelhantes fiquem próximos uns dos outros e respondam de maneira semelhante às entradas.
   O algorítmo foi desenvolvido em Python e o banco de dados está armazenado em um arquivo CSV.
   O banco de dados trata-se de um conjunto de pontos (20 de cada registro) que representam as posições dos dedos que foram capturados nas imagens.

## Desenvolvimento da Aplicação
### A ideia
   A ideia surgiu a partir de uma necessidade bem comum, como entender a Linguagem Brasileira de Sinais e participar do processo de inclusão de pessoas com deficit na oralidade, mas que já se comunicam através utilizando LIBRAS?
   Atualmente encontramos aplicativos nas Lojas de Aplicativos que conseguem, através de desenhos animados em 3D, processar linguagem natural e demonstrá-la em LIBRAS, o que facilita muita coisa. Porém, o contrário não é muito comum.
   Há uma necessidade de aplicações que realizem o processo inverso, para que a pessoa que utiliza gestos para se comunicar consiga fazê-lo esperando que seu espectador esteja entendendo.

### Produção do Banco de Dados para o Treinamento da Rede
   A partir das imagens selecionadas, utilizamos a biblioteca HandKeyPointerDetector para selecionar os pontos na imagem. Em seguida criamos um laço de repetição para selecionar cada imagem, obter os pontos e armazená-los em um arquivo CSV.
```
for i in range(nPoints):
  # confidence map of corresponding body's part.
  probMap = output[0, i, :, :]
  probMap = cv2.resize(probMap, (frameWidth, frameHeight))
  # Find global maxima of the probMap.
  minVal, prob, minLoc, point = cv2.minMaxLoc(probMap)
  if prob > threshold :
      cv2.circle(frameCopy, (int(point[0]), int(point[1])), 8, (0, 255, 255), thickness=-1, lineType=cv2.FILLED)
      cv2.putText(frameCopy, "{}".format(i), (int(point[0]), int(point[1])), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 255), 2, lineType=cv2.LINE_AA)
  # Add the point to the list if the probability is greater than the threshold
      points.append(int(point[0]))
      points.append(int(point[1]))
  else :
      points.append(0)
      points.append(0)

cv2.imwrite('Outputs/Rock/Output-Keypoints_'+str(j)+'.jpg', frameCopy)
#cv2.imwrite('Outputs/Palma/Output-Skeleton_'+str(j)+'.jpg', frame)

print("Total time taken : {:.3f}".format(time.time() - t))

print(points)

#Criar arquivo .csv
with open('keypointsRock.csv', mode='a') as employee_file:
  employee_writer = csv.writer(employee_file, delimiter=',', quotechar='"', quoting=csv.QUOTE_MINIMAL)
  employee_writer.writerow(points)

cv2.waitKey(0)
```
   Em seguida podemos ver exemplos de imagens utilizadas e os pontos encontrados pela biblioteca:
   

### Treinamento da Rede

### Experimentos e Aplicações Realizadas

## Concusão
