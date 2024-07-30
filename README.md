
# Titanic - Machine Learning from Disaster (Parte 1)


## Introdução

O naufrágio do Titanic é um dos naufrágios mais infames da história. Em 15 de abril de 1912, durante sua viagem inaugural, o RMS Titanic, amplamente considerado “inafundável”, afundou após colidir com um iceberg. Infelizmente, não havia botes salva-vidas suficientes para todos a bordo, resultando na morte de 1.502 dos 2.224 passageiros e tripulantes.

Embora houvesse algum elemento de sorte envolvido na sobrevivência, parece que alguns grupos de pessoas tinham maior probabilidade de sobreviver do que outros.



## Decrição do Projeto

Esse projeto trata-se de uma competição que ocorre em um dos sites mais famosos dentro da comunidade de dados, o **Kaggle**.

Neste projeto, será construido um modelo preditivo que responda à pergunta: 
- “Que tipos de pessoas têm maior probabilidade de sobreviver ao naufrágio do Titanic?” 
    - usando dados de passageiros (ou seja, nome, idade, sexo, classe socioeconômica, etc), tentaremos prever.

Os dados foram divididos em dois grupos:

- **conjunto de treinamento** (train.csv)
    - 890 registros 
    - Aproximadamente: 70%
    - Esse conjunto é usado para realizar o treinamento dos modelos e a validação.
- **conjunto de teste** (test.csv)
    - 417 registros 
    - Aproximadamente: 30%
    - Esse conjunto é usado para de fato testar a eficácia do classificador treinado
        - A resposta é obtida depois de submetida na plataforma do Kaggle.

O **conjunto de treinamento** deve ser usado para construir o modelo de aprendizado de máquina. Para o conjunto de treinamento, foi fornecido o resultado (também conhecido como “verdade básica”) para cada passageiro, onde é indicado quem sobreviveu (1) e quem não sobreviveu (0) . O modelo será baseado em “características” presentes na base de dados.

O **conjunto de testes** será usado para ver o desempenho do modelo em dados não vistos. Para o conjunto de testes, não será fornecido as informações dos passageiros que sobreviveram ou não. O trabalho é justamente prever esses resultados, onde para cada passageiro no conjunto de teste, será usado o modelo treinado para prever se eles sobreviveram ou não ao naufrágio do Titanic.

- Será analisado a acurácia do modelo, para determinar se o resultado é satisfatório ou não.

## Objetivo

Essa é a Parte 1 de um conjunto de análises feitas sobre este dataset. Em cada uma das partes, serão abordados métodos, análises ou tratativas de dados distintas, com o objetivo de aumentar a acurácia do resultado final.

## Metodologia

- Dado a quantidade de informações que o dataset gera, iremos fazer uma análise exploratoria nos dados, observando se ocorre uma melhora nos resultados a partir do momento que entramos em contato com mais métricas
- Nessa parte 1 foi feito:

    - **Importação da base**
    - **Uso ydata-profiling (ideia geral dos dados)**
    - **Limpeza de dados**
    - **Seleção e treinamento ds modelos para classificação**
        - Árvore de classificação
        - Classificação dos vizinhos mais próximos (KNN)
        - Regressão Logística
    - **Avaliação dos modelos**
        - Acurácia
        - Matriz de Confusão
    - **Realizando a previsão dos dados de Teste**
        - Submissão do projeto para a plataforma Kaggle, que é a responsavel por verificar a acurácia final com os dados de teste.

- A análise foi realizada em um arquivo **Jupyter Notebook**, então algumas explicações se encontram ao decorrer do arquivo.

- No diretorio também se encontra uma pasta **'dados'** com:
    - O conjunto de teste (*test.csv*) e o conjunto de treino (*train.csv*).
    - O arquivo da biblioteca (*ydata-profiling*) que auxilia na análise exploratória (*titanic_treino.html*).
    - E o arquivo com os dados que foram submetidos para análise no Kaggle (*base_envio.csv*).




## Conclusão

Neste projeto, que representa a Parte 1 de uma série de análises do dataset Titanic, realizamos diversas etapas para construir e avaliar modelos preditivos com o objetivo de determinar os fatores que influenciam a sobrevivência dos passageiros do Titanic. Através da importação e limpeza dos dados, do uso de ferramentas de análise exploratória como o ydata-profiling, e da implementação de vários modelos de classificação (Árvore de Decisão, K-Nearest Neighbors, Regressão Logística), conseguimos obter uma visão inicial das características mais relevantes e da performance dos modelos.

Os principais pontos abordados incluem:

- **Importação e limpeza de dados:** Garantimos que os dados estavam prontos para análise, removendo inconsistências e preenchendo valores ausentes.

- **Análise exploratória:** Utilizamos o ydata-profiling para obter uma visão geral dos dados e identificar padrões iniciais.
- **Seleção e treinamento de modelos:** Implementamos e treinamos modelos de classificação, ajustando parâmetros e avaliando suas performances.
- **Avaliação dos modelos:** Medimos a acurácia e analisamos as matrizes de confusão para entender melhor a eficácia dos modelos.
- **Previsão e submissão:** Aplicamos o modelo aos dados de teste e submetemos as previsões ao Kaggle para avaliação final.

Com esta abordagem inicial, conseguimos estabelecer uma linha de base para a acurácia dos nossos modelos. Em partes subsequentes deste projeto, continuaremos a explorar diferentes técnicas e tratamentos de dados para melhorar a performance preditiva.

O código e as análises detalhadas podem ser encontrados no arquivo Jupyter Notebook incluído neste repositório. À medida que avançamos para as próximas partes da série, esperamos refinar ainda mais nossos métodos e obter insights mais profundos sobre os fatores que influenciam a sobrevivência no desastre do Titanic.





## 🛠 Ferramentas
- Python 
- Bibliotecas 
    - Pandas
    - YData Profiling
    - Scikit Learn 
    - Seaborn
    - Matplotlib
    



## Autores

- [@pedrohspassos](https://github.com/pedrohspassos)



## Referências


 - [Ferramenta de análise exploratória](https://github.com/ydataai/ydata-profiling)
 - [Árvore de Decisão | scikit-learn](https://scikit-learn.org/stable/modules/tree.html#classification)
 - [Classificação dos vizinhos mais próximos (KNN) | scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html#sklearn.neighbors.KNeighborsClassifier)
 - [Regressão Logística | scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html#sklearn.linear_model.LogisticRegression)
- [Acurácia | scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html)
- [Matriz de Confusão | scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.confusion_matrix.html)

