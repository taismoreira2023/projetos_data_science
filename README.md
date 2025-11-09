# Projetos de Análise de Dados — Imóveis em SP & Estatística Descritiva com R

Este repositório reúne **dois projetos de análise de dados**, desenvolvidos com **Python** e **R**, voltados para estudos exploratórios, estatística descritiva, visualizações e geração de insights a partir de diferentes bases de dados.

---

#  1. Análise de Dados de Aluguéis de Imóveis em São Paulo

Este projeto realiza uma **análise exploratória de dados (EDA)** sobre imóveis alugados na cidade de São Paulo. O objetivo é compreender padrões do mercado de locação, características que influenciam os preços e comparações entre bairros e tipos de imóveis.

##  **Objetivo**

* Explorar variáveis relacionadas a imóveis para aluguel.
* Investigar tendências, correlações e distribuições.
* Obter insights úteis para corretores, inquilinos e investidores.

---

##  **Descrição dos Dados**

O dataset inclui as seguintes colunas:

* **address** – Endereço completo
* **district** – Bairro/região
* **area** – Área do imóvel (m²)
* **bedrooms** – Número de quartos
* **garage** – Número de vagas
* **type** – Tipo de imóvel
* **rent** – Valor do aluguel
* **total** – Valor total (aluguel + taxas)

Carregamento do arquivo:

```python
import pandas as pd
df = pd.read_csv('data.csv', sep=',')
```

---

##  **Tratamento e Limpeza**

* Remoção de imóveis com **área < 5 m²**
* Remoção de registros com **0 quartos**
* Verificação e tratamento de valores nulos

```python
df.isnull().sum()
df.describe()
```

---

##  **Análises Realizadas**

### **Estatísticas Descritivas**

* Área média/máxima/mínima
* Aluguel médio por tipo de imóvel
* Média de custo total por bairro

### **Distribuições**

* Quartos
* Vagas de garagem
* Tipos de imóvel
* Imóveis por bairro

### **Correlações**

* Área × Aluguel

  ```python
  df[['area','rent']].corr()
  ```

### **Comparações por Grupo**

* Bairros mais caros x mais baratos
* Custo total por tipo de imóvel

---

## **Visualizações**

Foram criados gráficos usando **Matplotlib** e **Seaborn**, como:

* Distribuição de quartos
* Aluguel médio por tipo
* Top 15 bairros com maior custo total
* Comparações entre bairros

Exemplo:

```python
plt.bar(categoria, valores, color='orange')
plt.title("Comparação do Aluguel Médio por Tipo de Imóvel")
```

---

## **Insights Obtidos**

* Imóveis maiores têm **aluguel mais alto**.
* Bairros como **Alphaville** possuem os maiores valores.
* Garagem aumenta significativamente o custo total.

---

## Como Rodar o Projeto

```bash
pip install pandas matplotlib seaborn
python analise_imoveis.ipynb
```

---

---

# 2. Estatística Descritiva com R

Este projeto apresenta uma análise estatística descritiva utilizando uma base extraída de um arquivo Excel **(Base2025.1.xlsx)**. As análises incluem tabelas de frequência, medidas de posição, dispersão e diversos tipos de gráficos.

## Arquivo Principal

* **Estatistica_descritiva.ipynb** — Notebook em R com toda a análise.

---

## **Pacotes Utilizados**

```r
install.packages("readxl")
install.packages("dplyr")
install.packages("xtable")

library(readxl)
library(dplyr)
library(xtable)
```

---

## **Análises Realizadas**

### **Tabelas de Frequência**

* Natureza
* Meio Empregado
* Gênero
* Escolaridade da Vítima
* Raça
* Dia da Semana

### **Tabelas Cruzadas**

* Meio Empregado × Gênero
* Escolaridade × Raça

### **Gráficos**

* Pizza: Gênero, Meio Empregado
* Barras: Dia da Semana, Escolaridade
* Linhas: Registro por Ano e Hora
* Boxplot: Idade da Vítima

### **Medidas de Posição e Dispersão**

* Média, Moda, Mediana
* Quartis
* Variância e desvio padrão
* Amplitude

---

## **Dataset**

O arquivo **Base2025.1.xlsx** contém dados estatísticos sobre crimes, incluindo:

* Natureza
* Meio usado
* Dados demográficos da vítima
* Data e hora do registro

---

## Como Executar no Google Colab

1. Fazer upload do notebook **Estatistica_descritiva.ipynb**
2. Alterar o ambiente para R:
   *Ambiente de execução → Alterar tipo → R*
3. Fazer upload da base **Base2025.1.xlsx**

---

# Colaboração

Projeto desenvolvido em equipe com **João Ava**.

---

# Tecnologias Utilizadas

### Python

* Pandas
* Matplotlib
* Seaborn

### R

* readxl
* dplyr
* xtable

---

