# Tasks-Pos-Graduacao-em-Data-Science
Irei popular esse repositório com as tasks realizadas durante a pós-graduação em Data Science pela Universidade Tecnológica Federal do Paraná.

## Deep Learning

Para disciplina de Deep Learning, todos os detalhes sobre o algoritmo utilizado (funções de ativação, otimizadores, etc) estão contidos no Colab. Reservarei esse espaço para algumas discussões gerais sobre a escolha das arquiteturas dos modelos. 

Começarei com uma task na qual apliquei uma CNN (Convolutional Neural Network) para classificar imagens da base CIFAR-10 (https://www.cs.toronto.edu/~kriz/cifar.html). Esse dataset é uma coleção de 60.000 imagens coloridas de 32x32 pixels, divididas em 10 classes diferentes, com 6.000 imagens por classe. Essas classes incluem aviões, automóveis, pássaros, gatos, veados, cães, sapos, cavalos, navios e caminhões, e são mutuamente exclusivas.

Essa base é mais desafiadora que outras de classificação de imagens, como a Fashion MNIST (https://github.com/zalandoresearch/fashion-mnist), por exemplo, a qual traz um conjunto de imagens em escala de cinza. 

Para classificar essas imagens, foram utilizadas duas arquiteturas de camadas. 

### Primeira arquitetura - semelhante a VGG-16

A primeira, semelhante à VGG-16, porém mais simples, com menor número de camadas e imagens de entrada de dimensões mais reduzidas.São 6 camadas de convolução, duas de pooling, uma flatten e duas fully-connected. Use um window size de (2 x 2) para a camada de pooling. Atenção para a função de ativação SoftMax na última camada fully-connected.

![image](https://github.com/leticiacanton/Tasks-Pos-Graduacao-em-Data-Science/assets/38925042/a52f3923-3b5f-4884-ac4c-6a4be9ab1e94)

Porém, como pode ser visto no Colab, o modelo apresenta overfitting. 

![image](https://github.com/leticiacanton/Tasks-Pos-Graduacao-em-Data-Science/assets/38925042/4ffdf298-34ca-4e8e-868d-7f9fa5374ba2)

O gráfico que relaciona a curva de loss (perda de treinamento) com a curva de validation loss (perda de validação) mostra que, quando se adiciona um número maior de exemplos para o treinamento, a perda de validação começar a aumentar, o que representa um sinal de overfitting. O overfitting ocorre quando o modelo se ajusta excessivamente aos dados de treinamento, memorizando eles ao invés de aprender os padrões gerais, o que pode levar a um desempenho inferior em dados não vistos.

Portanto, quando a perda de treinamento e a perda de validação não se aproximam, isso mostra que o modelo não está bem ajustado aos dados de treinamento e, consequentemente, não tem um bom desempenho em dados não vistos. Outro indicativo de overfitting no modelo é que a acurácia no treinamento chega a 98%, enquanto na validação chega apenas em 77%.

Ao final, essa foi a matriz de confusão obtida com a arquitetura proposta, com uma acurácia de 63%.

![image](https://github.com/leticiacanton/Tasks-Pos-Graduacao-em-Data-Science/assets/38925042/8b5979b5-aaee-41d0-a61f-7b057f122f6d)

Todavia o overfitting é uma preocupação, mesmo que a acurácia nos dados de teste tenha sido boa. Sendo assim, o recomendado seria aprimorar o modelo, para tentar melhorar sua capacidade de generalização e reduzir o impacto do overfitting.





