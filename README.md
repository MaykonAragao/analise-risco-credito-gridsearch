# 🏦 Análise de Risco de Crédito com Otimização de Hiperparâmetros

![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-brightgreen)

## 📄 Descrição do Projeto

Este projeto aborda o desafio de **classificação de risco de crédito**, um problema fundamental no setor financeiro. O objetivo foi desenvolver um pipeline de Machine Learning robusto, com foco em duas técnicas avançadas: o uso de **Pipelines** para um pré-processamento seguro e a **otimização de hiperparâmetros com `GridSearchCV`** para extrair a melhor performance possível de um modelo `RandomForestClassifier`.

## 📊 Dataset

O dataset utilizado foi o "German Credit Data", contendo informações sobre 1000 concessões de crédito, classificadas como "bom" ou "mau" risco. O dataset apresenta desafios do mundo real, como dados faltantes e uma mistura de variáveis numéricas e categóricas.

*   **Link para o Dataset:** [German Credit Risk](https://www.kaggle.com/datasets/kabure/german-credit-data-with-risk)

## 🛠️ Ferramentas e Técnicas Utilizadas

*   **Linguagem:** Python 3
*   **Bibliotecas:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn.
*   **Técnicas Chave:**
    *   **Pipelines e `ColumnTransformer`:** Para criar um fluxo de pré-processamento que lida com imputação de dados faltantes, encoding de variáveis categóricas (`OneHotEncoder`) e dimensionamento de features (`StandardScaler`), tudo de forma organizada e segura contra *data leakage*.
    *   **Otimização de Hiperparâmetros:** `GridSearchCV` foi utilizado para testar sistematicamente várias combinações de parâmetros do `RandomForestClassifier` (`n_estimators`, `max_depth`, etc.), com o objetivo de otimizar a métrica **`recall`**.
    *   **Métrica de Negócio:** A otimização focou no **`recall`**, pois para uma instituição financeira, o custo de aprovar um empréstimo de alto risco (Falso Negativo) é muito maior do que o custo de negar um bom empréstimo (Falso Positivo).

## 📈 Resultados do Modelo Otimizado

Após a busca em grade, o melhor modelo encontrado foi avaliado no conjunto de teste, apresentando os seguintes resultados para a classe de interesse (`Risk = 1`, clientes de "mau" risco):

*   🎣 **Recall de 36%:** O modelo otimizado foi capaz de identificar **36% de todos os clientes que de fato representavam um risco**.
*   🎯 **Precisão de 45%:** Quando o modelo sinaliza um cliente como "de risco", ele está correto 45% das vezes.

### Análise dos Resultados

Embora a performance possa ser melhorada, o resultado estabelece um **baseline sólido e realista**. Um recall de 36% já representa um valor de negócio tangível, permitindo ao banco identificar proativamente mais de um terço dos empréstimos problemáticos. A conclusão do projeto aponta para os próximos passos, como a aplicação de engenharia de features e o teste de algoritmos mais avançados como o **XGBoost**.

## 🚀 Como Executar o Projeto

1.  Clone este repositório.
2.  Instale as dependências (`pip install pandas numpy scikit-learn matplotlib seaborn`).
3.  Execute o notebook `analise_risco_credito.ipynb` em um ambiente Jupyter.
