# 🧠 Otimização de Cupons com Machine Learning — iFood Case

⚠️ Atenção: o arquivo transactions.json deve ser baixado manualmente e inserido na pasta data/raw/, pois o tamanho total impede a inclusão no repositório.

## 📌 Visão Geral

Este projeto simula um desafio real enfrentado por plataformas como o iFood: **otimizar o envio de cupons e ofertas promocionais para aumentar conversão e reduzir desperdício**. Utilizando dados históricos de clientes, ofertas e transações, aplicamos técnicas de análise exploratória, engenharia de atributos e machine learning para prever o **nível de engajamento de cada cliente com campanhas de cupons**.

---

## 🎯 Objetivo

Criar um modelo preditivo capaz de **classificar os clientes em três níveis de engajamento** com cupons:

* `0`: baixo engajamento (ignora ofertas)
* `1`: médio engajamento (visualiza, mas não completa)
* `2`: alto engajamento (usa cupons com frequência)

Essa classificação permite à empresa:

* **Evitar o envio de cupons a quem não converte**
* **Focar em quem realmente responde às campanhas**
* **Aumentar a eficiência do investimento em marketing**

---

## 🔍 Etapas do projeto

### 1. Análise exploratória (EDA)

* Unificação e limpeza das bases de clientes, transações e ofertas.
* Tratamento de valores nulos, outliers e validação de consistência entre eventos.
* Transformação de variáveis temporais e comportamentais.

### 2. Engenharia de atributos

* Criação de variáveis como:

  * Taxa de visualização e conclusão de cupons
  * Gastos médios, totais e desvio padrão
  * Interação com diferentes canais (email, web, mobile)
  * Tipo de oferta preferido
* Segmentação dos clientes com base em engajamento histórico.

### 3. Modelagem

* Testamos dois modelos principais:

  * **Random Forest** (baseline)
  * **Logistic Regression com regularização** (final escolhido)
* Avaliamos acurácia, F1-score e sensibilidade às classes desbalanceadas.
* Aplicamos **oversampling da classe 0** para melhorar detecção de clientes desengajados.

### 4. Resultados

* Modelo final com:

  * **98.9% de acurácia**
  * **98.4% de F1-score**
* Passou a reconhecer clientes de baixo engajamento que antes eram ignorados.
* Gerou insights acionáveis sobre o comportamento por canal e tipo de cupom.

---

## ⚙️ Stack utilizada

* **Linguagem**: Python
* **Processamento distribuído**: PySpark (em ambiente Databricks)
* **Visualização e validação**: Pandas, Seaborn, Sklearn (auxiliar)
* **Modelo final**: `LogisticRegression` do `pyspark.ml.classification`

---

## 📈 Impacto estimado da estratégia

| Métrica                                 | Estimativa   |
| --------------------------------------- | ------------ |
| Redução de cupons enviados sem retorno  | até **40%**  |
| Aumento na taxa de uso de cupons        | até **25%**  |
| Aumento estimado de conversão em vendas | **8% a 12%** |
| Precisão média do modelo                | **98.9%**    |

---

## 💡 Conclusão

Com o modelo desenvolvido, é possível tornar as campanhas promocionais do iFood muito mais inteligentes, personalizadas e rentáveis. A IA atua como uma **ferramenta de apoio à tomada de decisão em marketing**, ajudando a entregar a oferta certa, para o cliente certo, no momento certo.

---

## 🚀 Próximos passos (sugeridos)

* Integração com ferramentas de automação de campanhas.
* Avaliação contínua do modelo com dados atualizados.
* Implementação de testes A/B com base nas predições.
* Exploração de técnicas de recomendação personalizadas.

---

## ▶️ Como executar este projeto

### ✅ Opção 1: Executar no [Databricks Community Edition](https://community.cloud.databricks.com/)

1. Crie uma conta gratuita no Databricks.
2. Importe o notebook do projeto.
3. Crie um cluster com **Runtime 11.3 LTS ou superior** (com suporte a Spark 3.4+).
4. Faça upload dos arquivos `.json` na pasta `/FileStore/` ou `/dbfs/`.
5. Execute o notebook célula por célula. As bibliotecas PySpark já vêm pré-instaladas.

### ✅ Opção 2: Executar localmente

> Recomendado apenas se você tiver familiaridade com PySpark em ambiente local.

#### Pré-requisitos:

* Python 3.8+
* Java 8 ou superior
* PySpark 3.4+ instalado



