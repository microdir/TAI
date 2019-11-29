# Reconhecimento de Gestos em Libras

## Introdução
	O relatório a seguir tem o objetivo de mostrar ao leitor um breve histórico do processo de desenvolvimento de um algorítimo, escrito pelos alunos João Marcos e Michel Rodrigo, que é capaz de reconhecer gestos em Libras (Linguagem Brasileira de Sinais).
	O projeto foi desenvolvido como atividade final da disciplina de Tópicos Avançados em Informática na Escola de Ciência e Tecnologia da UFRN, ministrada pelo professor Orivaldo Santana.
	É importante salientar que o objetivo foi cumprido (reconhecer os gestos), porém, não é algo simples o suficiente para ser concluído com tanta rapidez. Portanto, o algorítimo reconhece gestos de algumas letras do alfabeto em libras, mas com um pouco de refino e um banco de dados mais apurado tem potencial para conseguir reconhecer ainda mais.

## Metodologia
	O modelo de Machine Learning utilizado no processo foi o da rede SOM (Self-Organized-Maps), que, de cordo com PINHEIRO (2019) “é uma rede neural de 2 camadas que aceita padrões de N-dimensões como entrada e os mapeia para um conjunto de neurônios de saída, o qual representa o espaço dos dados a serem agrupados”.
	A ideia principal desse modelo é fazer com que dados semelhantes fiquem próximos uns dos outros e respondam de maneira semelhante às entradas.
	A linguagem de programação utilizada foi a Python e o banco de dados está armazenado em um arquivo CSV.
	O banco de dados trata-se de um conjunto de pontos (20 de cada registro) que representam as posições dos dedos que foram capturados nas imagens.

## Desenvolvimento da Aplicação
### A ideia
	A ideia surgiu a partir de uma necessidade bem comum, como entender a Linguagem Brasileira de Sinais e participar do processo de inclusão de pessoas com deficit na oralidade, mas que entendem LIBRAS.
	Atualmente encontramos aplicativos nas Lojas de Aplicativos que conseguem, através de desenhos animados em 3D, processar linguagem natural e demonstrá-la em LIBRAS, o que já facilita bastante. Porém, o contrário não é muito comum.
	Há uma necessidade de aplicações que realizem o processo inverso, para que a pessoa que utiliza gestos para se comunicar, consiga fazê-lo sem se preocupar o quanto seu espectador esteja entendendo.

### Produção do Banco de Dados para o Treinamento da Rede
	O banco de dados foi produzido em casa. Utilizamos nossos celulares para capturar, em vídeo, os gestos reais que representam as letras do alfabeto em Libras. Os vídeos foram tratados de modo a dividi-lo em 25 frames por segundo. Tendo sido gravado dois vídeos, obtemos um banco de imagens com 50 frames de cada letra.
	O passo seguinte foi utilizar um algorítimo que encontrasse os pontos desejados e os passasse para um arquivo CSV. 

### Treinamento da Rede

### Experimentos e Aplicações Realizadas

## Concusão
