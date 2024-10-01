# Previsão de Popularidade de Músicas com Machine Learning

Este projeto tem como objetivo prever a popularidade de músicas utilizando técnicas de Machine Learning, mais especificamente o algoritmo Árvore de Decisão e Random Forest. O projeto envolve desde a análise exploratória dos dados até a implementação de um modelo preditivo e o ajuste fino de seus hiperparâmetros para melhorar o desempenho.

## Estrutura do Projeto
### 1. Análise Exploratória de Dados (EDA)

- Inicialmente, foi realizada a carga e a exploração dos dados através da biblioteca pandas. Verificamos informações básicas do conjunto de dados e fizemos uma análise inicial das variáveis. Algumas etapas incluem a visualização de distribuições, remoção de outliers e conversão de unidades de medida (como a duração da música de milissegundos para minutos).

### 2. Pré-processamento dos Dados

- Para aplicar os modelos de machine learning, foi necessário fazer o pré-processamento dos dados. Isso incluiu a codificação de variáveis categóricas como 'artists' e 'track_genre' utilizando LabelEncoder, além da normalização e padronização de variáveis numéricas.
- Também removemos outliers das variáveis para garantir que o modelo não fosse influenciado por dados atípicos.

### 3. Modelagem com Árvore de Decisão

- Foi o algoritmo de Árvore de Decisão para construir um modelo de classificação.
- Foi realizado a divisão dos dados em conjunto de treino e teste utilizando train_test_split.
- Após o treinamento, o desempenho do modelo foi avaliado utilizando métricas como Acurácia, Matriz de Confusão, e Relatório de Classificação.

### 4. Ajuste de Hiperparâmetros

- Para otimizar o desempenho do modelo, foi utilizado o GridSearchCV para realizar a busca dos melhores hiperparâmetros, tais como criterion, max_depth, min_samples_split, e min_samples_leaf.
- Foram testados diferentes valores para esses hiperparâmetros para obter o melhor modelo possível.

### 5. Importância das Features

- Utilizando o modelo de Árvore de Decisão, foi gerado um gráfico que mostra a importância das features (variáveis independentes). Este gráfico ajuda a identificar quais variáveis têm maior impacto na previsão da popularidade de uma música.

### 6. Testes com Random Forest

- Além da árvore de decisão, também aplicamos o modelo de Random Forest, que é um conjunto de várias árvores de decisão. Isso normalmente melhora a robustez e o desempenho do modelo.
Avaliamos a performance e ajustamos os hiperparâmetros do Random Forest para obter melhores previsões.

### 7. Geração de Arquivo CSV com Resultados

- O arquivo test.csv foi utilizado para prever a popularidade de músicas a partir do modelo treinado. Geramos um arquivo de saída que contém os IDs das músicas e o booleano popularity_target, indicando se a música é popular ou não.

## Instruções para Executar o Projeto

Clone este repositório no terminal utilizando git:

```
git clone clone https://github.com/JvWandermurem/Modelo-Preditivo.git
```

Execute o notebook 
```
jupyter notebook notebook.ipynb
```

Certifique-se de que os arquivos train.csv e test.csv estão no mesmo diretório do notebook.

## Principais Bibliotecas Utilizadas

- **pandas:** Para manipulação de dataframes.
- **numpy:** Para operações matemáticas.
- **matplotlib e seaborn:** Para visualização de dados.
- **scikit-learn:** Para modelagem, avaliação e ajuste fino de hiperparâmetros.
- **shap:** Para visualização de explicações de modelos.

## Estrutura dos Dados
train.csv: Conjunto de treino que contém as features (variáveis independentes) e o alvo (popularidade da música).
test.csv: Conjunto de teste que contém apenas as features, para prever a popularidade.
Features Presentes no arquivo csv: 
 | Column             | Dtype   |
|--------------------|---------|
| track_unique_id               | int64   |
| track_id                      | object  |
| artists                       | object  |
| album_name                    | object  |
| track_name                    | object  |
| duration_ms                   | int64   |
| explicit                      | bool    |
| danceability                  | float64 |
| energy                        | float64 |
| key                           | int64   |
| loudness                      | float64 |
| mode                          | int64   |
| speechiness                   | float64 |
| acousticness                  | float64 |
| instrumentalness              | float64 |
| liveness                      | float64 |
| valence                       | float64 |
| tempo                         | float64 |
| time_signature                | int64   |
| track_genre                   | object  |
| popularity_target             | int64   |


## Métricas de Avaliação
- Acurácia: Percentual de previsões corretas.
- Matriz de Confusão: Representação do desempenho das previsões de classes.
- Relatório de Classificação: Inclui métricas de precisão, recall e F1-score.

## Resultados
O projeto conseguiu desenvolver um modelo preditivo eficaz para identificar a popularidade de músicas, com a árvore de decisão sendo aprimorada pelo ajuste fino dos hiperparâmetros e a inclusão de técnicas de ensemble como Random Forest.

## Melhorias Futuras
- Explorar outros modelos de machine learning, como Gradient Boosting.
- Experimentar técnicas mais avançadas de feature engineering e seleção de features.
- Avaliar a integração de dados adicionais para melhorar as previsões.