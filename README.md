
# Titanic - Machine Learning from Disaster 

- Abaixo se encontra um preview do histórico obtido durante o desenvolvimento do projeto:

![img_resultado](https://github.com/user-attachments/assets/f3377bd0-77ce-4aea-8825-06649091a1b2)


## Introdução

O naufrágio do Titanic é um dos naufrágios mais infames da história. Em 15 de abril de 1912, durante sua viagem inaugural, o RMS Titanic, amplamente considerado “inafundável”, afundou após colidir com um iceberg. Infelizmente, não havia botes salva-vidas suficientes para todos a bordo, resultando na morte de 1.502 dos 2.224 passageiros e tripulantes.

Embora houvesse algum elemento de sorte envolvido na sobrevivência, parece que alguns grupos de pessoas tinham maior probabilidade de sobreviver do que outros.



## Decrição do Projeto

Esse projeto trata-se de uma competição que ocorre em um dos sites mais famosos dentro da comunidade de dados, o **Kaggle**.

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

Desenvolver um modelo que conseguisse acertar quais passageiros sobreviveram ou não ao naúfragio do Titanic. Para isso, aquele que obtivesse a maior **acurácia** seria o escolhido.

## Etapas

- ## [Etapa 1 - Primeiro modelo](https://github.com/pedrohspassos/predicted-survivors-titanic/blob/main/analise_titanic_parte1.ipynb)
    - Nesse etapa foi feito apenas o básico para conseguir verificar qual seria o resultado sem fazer nenhum tratamento nem engenharia dos dados
      - Foi visualizado um resumo da base utilizando o [ydata-profiling](https://github.com/ydataai/ydata-profiling), biblioteca capaz de gerar com poucas linhas toda a descrição do nosso dataset
      - Também foi elimido as colunas com elevada cardinalidade, foi tratado os valores vazios utilizando a média e a moda das variáveis e foi eliminado todas as colunas de texto
      - Foram criados modelos utilizando 3 algoritmos: Árvore de Classificação, KNN e Regressão Logística, nos quais foram avaliados utilizando a acurácia e a matriz de confusão
  - **O score público retornado pelo Kaggle foi: 0,66746**
    
- ## [Etapa 2 - Tratando as variáveis de texto](https://github.com/pedrohspassos/predicted-survivors-titanic/blob/main/analise_titanic_parte2.ipynb)
    - Na segunda etapa o foco principal foi tratar as variáveis de texto para que fosse possível utilizar todas as variáveis no modelo
        - Para fazer esse tratamento, utilizamos **lambda function** e **OneHotEncoder**
    - Foram utilizados os mesmos modelos apresentados anteriormente
    - **O score público retornado pelo Kaggle foi: 0,76555**

- ## [Etapa 3 - Aprofundando no negócio e melhorando os tratamentos dos dados](https://github.com/pedrohspassos/predicted-survivors-titanic/blob/main/analise_titanic_parte3.ipynb)
    - Nessa terceira etapa o grande objetivo era entender melhor os dados para fazer um melhor tratamento e tentar melhorar o resultado obtido anteriormente
    - Logo, foi feito:
        - O **ajuste na escala dos dados para as colunas Age e Fare**
        - O entendimento melhor sobre as colunas **SibSp** (nº de irmãos/cônjuges a bordo do Titanic) e **Parch** (nº de pais/filhos a bordo do Titanic) e a criação de **duas novas colunas: total de familiares a bordo do navio e se o passageiro estava sozinho ou não**
        - Por fim, foi analisado a **correlação de todas as variáveis para selecionar aquelas que mais faziam sentido para o modelo**
    - Foram utilizados os mesmos modelos apresentados anteriormente
    - **O score público retornado pelo Kaggle foi: 0,77033**
      
- ## [Etapa 4 - Selecionando outros algoritmos para fazer a previsão](https://github.com/pedrohspassos/predicted-survivors-titanic/blob/main/analise_titanic_parte4.ipynb)
    - Nessa etapa, foram mantidas todas as colunas (incluindo SibSp e Parch) e foram usados novos algoritmos para verificar o resultado do modelo
    - Os algoritmos utilizados nessa etapa são **RandomForest , MLPCLassifier (Redes Neurais) e Regressão Logística** (mantida devido seus bons resultados ao decorrer das etapas)
    - O MLPClassifier (um algoritmo de Redes Neurais) obteve a maior acurácia nos dados de validação entre todos os modelos vistos até anteriormente, porém ao usar esse modelo nos dados de teste (submetidos no Kaggle) o resultado foi pior que na etapa 3, mostrando que provavelmente tivemos um **overfitting do nosso modelo**
    - **O score público retornado pelo Kaggle foi: 0,69856**
      
- ## [Etapa 5 - Utilizando o GridSearchCV e determinando os melhores parâmetros](https://github.com/pedrohspassos/predicted-survivors-titanic/blob/main/analise_titanic_parte5.ipynb)
    - Foi utilizado o **GridSearchCV** para determinar os melhores parâmetros para os 3 modelos que foram utilizados na etapa anterior
    - Nesse caso, o modelo escolhido foi aquele que utilizava o **RandomForest** e o resultado melhorou consideravalmente em relação a etapa 4 e foi melhor que na etapa 3
    -  - **O score público retornado pelo Kaggle foi: 0,78229**






## Conclusão







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

