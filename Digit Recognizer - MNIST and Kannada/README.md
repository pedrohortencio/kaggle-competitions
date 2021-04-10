# Sobre Este Repositório

Há duas atividades principais que constam nos arquivos deste repositório:
1) A participação na competição [Digit Recognizer](https://www.kaggle.com/c/digit-recognizer), do Kaggle.
2) A comparação de resultados de um mesmo modelo, do tipo Convolutional Neural Network, no dataset do MNIST (da competição mencionada acima) e do Kannada MNIST. 

Os notebooks da competição do Kaggle são os:
* [Digit Recognizer - CNN](https://github.com/pedrohortencio/digit-recognizer-kaggle/blob/master/Digit_Recognizer_CNN.ipynb) - implementa uma CNN para a resolução do desafio.
* [Digit Recognizer - SVC](https://github.com/pedrohortencio/digit-recognizer-kaggle/blob/master/Digit_Recognizer_SVC.ipynb) - implementa um SVC para a resolução do desafio.

Os resultados obtidos pelos notebooks foram descritos mais abaixo, após os resultados da comparação entre os datasets.

# Comparação de Resultados entre o Dataset MNIST e Kannada MNIST 
## Sobre os Dados
O dataset MNIST é um clássico da visão computacional, sendo, inclusive, chamado de o "Hello World" da inteligência artificial.

Já o dataset Kannada MNIST é uma evolução, contendo numerais arábicos. O dataset pode ser encontrado, com mais detalhes, na página do [Kaggle](https://www.kaggle.com/c/Kannada-MNIST).

## Sobre a Comparação
Por simples curiosidade, decidi comparar a performance de um modelo padrão nos dois datasets. O modelo é igual para os dois datasets, treinado sob a mesma condição de parada:
quando a *validation loss* decair por 3 épocas.

### Resultados

Com uma surpresa inicial, o modelo se saiu melhor no conjunto de dados do Kannata MNIST. Foi obtido menores valores de loss tanto no conjunto de validação, quanto no conjunto de testes. A acurácia do modelo também foi maior em ambos os conjuntos.

A conclusão preliminar para esses resultados é a maior variedade de exemplos de cada classe no conjunto de dados do Kannata MNIST. Devido à maior complexidade dos dígitos, há uma maior variação na forma como são escritos. Isso, possivelmente, foi responsável por fazer com que o modelo pudesse ter uma maior capacidade de abstração do que no conjunto de dados clássicos do MNIST.

Abaixo estão os gráficos com os resultados finais. Mais abaixo, estão os resultados obtidos na competição Digit Recognizer, do Kaggle, que julga a acurácia obtida no conjunto de dados MNIST.

 ![](https://raw.githubusercontent.com/pedrohortencio/digit-recognizer-kaggle/master/Validation-Loss-Comparison.png)
 *Evolução da validation loss de acordo com as épocas. Apenas as 30 primeiras sendo exibidas.*
 
 ![](https://raw.githubusercontent.com/pedrohortencio/digit-recognizer-kaggle/master/Validation-Accuracy-Comparison.png)
 *Evolução da acurácia no conjunto de validação ao longo das épocas. Apenas as 30 primeiras sendo exibidas.*
 
 ![](https://raw.githubusercontent.com/pedrohortencio/digit-recognizer-kaggle/master/Test-Loss-Comparison.png)
 *Loss final, obtida no conjunto de testes.*
 
 ![](https://raw.githubusercontent.com/pedrohortencio/digit-recognizer-kaggle/master/Test-Accuracy-Comparison.png)
  *Acurácia final, obtida no conjunto de testes.*
  
  

# Digit Recognizer Kaggle Competition
Criação de modelos para a resolução da competição do Kaggle relativa ao reconhecimento de dígitos escritos a mão. Foram criados dois modelos de machine learning: um Support Vector Classifier (SVC) e uma Convolutional Neural Network (CNN ou ConvNet).

O objetivo foi confrontar os resultados obtidos pelo modelo SVC, mais simples, e pela CNN, um modelo mais robusto.

## Sobre o problema
O dataset utilizado é o MNIST, um problema de visão computacional cujo objetivo é corretamente identificar dígitos escritos a mão sob a forma de imagens. O link da competição é: https://www.kaggle.com/c/digit-recognizer.

## Sobre o algoritmo SVC

No primeiro modelo criado, foi utilizado para a resolução do problema um Support Vector Classifier (um tipo de Support Vector Machine) para fazer a classificação. Como é um problema de várias classes (cada imagem pode ser categorizada em 10 classes, sendo uma para cada dígito) é utilizado o método One-Vs-One desse algoritmo.

Outros algoritmos usados juntamente do SVC incluem: o modelo de aprendizado não-supervisionado Principal Component Analysis (PCA) para diminuir a dimensão do problema e o GridSearchCV para encontrar a melhor combinação de parâmetros para o algoritmo de machine learning.

A acurácia obtida pelo modelo final foi 98.21% no dataset de validação e 98.12% no dataset de teste (reportado pelo Kaggle).

## Sobre o algoritmo CNN

Também foi criado um modelo de rede neural do tipo convolucional. Nesse caso, uma única camada de CNN e duas camadas densas produziram um modelo cuja acurácia alcançou 99.56% no conjunto de treino, 99.36% na validação e 99.114% de acurácia no conjunto de testes submetido ao Kaggle.

Utilizei a função de ativação LeakyReLU, uma implementação baseada na ReLU.

Esse modelo mostrou-se mais simples e rápido de ser treinado do que o SVC e com uma acurácia um pouco maior.

## Conclusão

Ambos os modelos tiveram uma ótima acurácia no problema. O SVC é uma ótima opção quando a quantidade de dados é pequena, enquanto a CNN é uma opção mais robusta quando há uma grande quantidade de dados (como o caso dessa competição).

Ambos os códigos foram feitos em Python, utilizando o pacote scikit-learn (sklearn) e a API Keras, baseada no TensorFlow. O ambiente de desenvolvimento utilizado foi o Google Colab, uma implementação da Google do Jupyter Notebook.
