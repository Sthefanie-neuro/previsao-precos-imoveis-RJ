# Previsão de Preços de Imóveis no Rio de Janeiro com PySpark

## 📝 Descrição do Projeto

Este projeto tem como objetivo desenvolver um modelo de Machine Learning para prever o preço de imóveis localizados na cidade do Rio de Janeiro. Utilizando um grande volume de dados, aplicamos técnicas de processamento distribuído com **Apache Spark** para tratar, transformar e modelar os dados, buscando a maior acurácia possível na previsão de valores.

O notebook explora todo o ciclo de vida de um projeto de Data Science, desde a limpeza e preparação dos dados, passando pela engenharia de atributos, até o treinamento, otimização e avaliação de múltiplos modelos de regressão.

### Créditos e Contexto

Este projeto foi desenvolvido como parte do curso **"Spark: trabalhando com regressão"** da [Alura](https://www.alura.com.br). Agradecimentos especiais a toda a equipe e instrutores da Alura pelo conteúdo de alta qualidade e pelo suporte fundamental durante o aprendizado.

## 🚀 Tecnologias Utilizadas

- **Apache Spark & PySpark:** Para processamento de dados em larga escala e computação distribuída.
- **PySpark MLlib:** Para construção, treinamento e avaliação dos modelos de Machine Learning.
- **Pandas:** Para manipulação de dados e conversão para visualização.
- **Matplotlib & Seaborn:** Para análise exploratória e visualização dos resultados dos modelos.
- **Google Colab:** Como ambiente de desenvolvimento e execução do notebook.

## 📂 Estrutura do Projeto

O fluxo de trabalho desenvolvido no notebook segue as seguintes etapas:

1.  **Configuração do Ambiente:** Inicialização da `SparkSession` e importação das bibliotecas necessárias.
2.  **Carregamento e Limpeza de Dados:** Leitura do dataset e aplicação de filtros iniciais (seleção de imóveis do Rio de Janeiro).
3.  **Engenharia de Atributos:** Transformação de variáveis categóricas (`unit`, `zone`) em formato numérico através de pivoteamento (One-Hot Encoding).
4.  **Pré-processamento:** Consolidação de todos os atributos em um único vetor de features utilizando o `VectorAssembler`.
5.  **Treinamento de Modelos:** Treinamento de dois modelos de regressão:
    * `DecisionTreeRegressor` (Árvore de Decisão)
    * `RandomForestRegressor` (Florestas Aleatórias)
6.  **Otimização de Hiperparâmetros:** Uso de `ParamGridBuilder` e `CrossValidator` para encontrar as melhores configurações para cada modelo, evitando overfitting e melhorando a capacidade de generalização.
7.  **Avaliação dos Modelos:** Comparação dos modelos com base nas métricas **R² (R-quadrado)** e **RMSE (Raiz do Erro Quadrático Médio)**.
8.  **Análise Visual:** Geração de gráficos comparativos (Previsto vs. Real e Gráfico de Resíduos) para uma análise qualitativa do desempenho do melhor modelo.

## 🛠️ Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git](https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git)
    ```
2.  **Ambiente:** Abra o notebook `Spark_previsao_imoveis.ipynb` em um ambiente compatível, como o Google Colab.
3.  **Dataset:** Faça o upload do arquivo de dados (`dataset.csv`) para o ambiente de execução.
4.  **Execução:** Execute as células do notebook em sequência.

## 📈 Resultados

Após o treinamento e a otimização com validação cruzada, o modelo **Random Forest Regressor** apresentou um desempenho superior ao Decision Tree, tornando-se o modelo final escolhido. As métricas de avaliação no conjunto de teste foram:

* **R² (R-quadrado):** [0.831605]
* **RMSE (Raiz do Erro Quadrático Médio):** [562157.227221]

A análise visual dos resíduos confirmou que o modelo Random Forest possui erros mais distribuídos aleatoriamente, indicando um bom ajuste aos dados.

## 🔮 Prevendo Resultados com o Melhor Modelo

Com o modelo `RandomForestRegressor` treinado e otimizado, podemos utilizá-lo para prever o preço de um novo imóvel. Para isso, basta fornecer as características do imóvel de interesse.

### Exemplo de Previsão

Abaixo, simulamos a previsão para um imóvel com as seguintes características:

* **Banheiros (`bathrooms`):** 2
* **Quartos (`bedrooms`):** 3
* **Andares (`floors`):** 2
* **Espaço de garagem (`parkingSpaces`):** 1
* **Suítes (`suites`):** 1
* **Andar (`unitFloor`):** 2
* **Unidades por andar (`unitOnTheFloor`):** 1
* **Área usável (`usableAreas`):** 150
* **Valor de condôminio (`condo`):** 400
* **Valor IPTU (`iptu`):** 0
* **Apartamento (`Apartamento`):** 1
* **Casa (`Casa`):** 0
* **Outros (`Outros`):** 0
* **Zona Central (`Zona Central`):** 0
* **Zona Norte (`Zona Norte`):** 0
* **Zona Oeste (`Zona Oeste`):** 0
* **Zona Sul (`Zona Sul`):** 1
* **Preço (`label`):** 0

> **Resultado da Previsão:**
>
> ## **Valor Previsto: R$ [1871882.07]**

Este resultado demonstra a aplicação prática do modelo em um cenário real, fornecendo uma estimativa de preço com base nas features fornecidas.

## ✍️ Autor e Agradecimentos

Este projeto foi desenvolvido por:

* **Sthefanie Ferreira de S. D. Otaviano** - [LinkedIn](https://linkedin.com/in/sthefanie-ferreira-de-s-d-otaviano-976a59206)

Agradeço a toda a equipe da Alura pelo suporte e pela qualidade do conteúdo que tornou este projeto possível.

Um agradecimento especial ao instrutor **Pedro Henrique Campagna Moura da Silva** pela excelente didática e orientação ao longo do curso "Spark: trabalhando com regressão".
