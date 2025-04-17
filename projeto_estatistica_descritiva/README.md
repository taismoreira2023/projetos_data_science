
# Estatística Descritiva com R

Este repositório contém um notebook em R que realiza uma análise estatística descritiva sobre um conjunto de dados extraído de um arquivo Excel (`Base2025.1.xlsx`). A análise contempla desde tabelas de frequência até medidas de posição, dispersão e visualizações gráficas.

---

## Arquivo Principal

- `Estatistica_descritiva.ipynb`: notebook em R com a análise estatística.

---

## Pacotes Utilizados

O notebook utiliza os seguintes pacotes R:

```r
install.packages("readxl")
install.packages("dplyr")
install.packages("xtable")

library(readxl)
library(dplyr)
library(xtable)
```

---

## Análises Realizadas

### Tabelas de Frequência (simples e relativas)
Para as variáveis:
- Natureza
- Meio Empregado
- Gênero
- Escolaridade da Vítima
- Raça da Vítima
- Dia da Semana

### Tabelas Cruzadas
- Meio Empregado × Gênero
- Escolaridade da Vítima × Raça da Vítima

### Gráficos
- **Setor (pizza)**: Gênero, Meio Empregado
- **Barras**: Dia da Semana, Escolaridade da Vítima
- **Linhas**: Registros por Ano, Registros por Hora
- **Boxplot**: Idade da Vítima

### Medidas de Posição
- Moda
- Média
- Mediana
- Quartis

### Medidas de Dispersão
- Variância
- Desvio Padrão
- Amplitude

---

## Dataset

O conjunto de dados `Base2025.1.xlsx` contém registros de crimes com informações sobre:
- Natureza do crime
- Meio utilizado
- Características da vítima (gênero, idade, raça, escolaridade)
- Data e hora do crime

---

## Execução

Este notebook pode ser executado via Google Colab com suporte a R. Para isso:
1. Faça upload do `Estatistica_descritiva.ipynb` no Colab.
2. Certifique-se de alterar o runtime para R (`Ambiente de execução` > `Alterar tipo de ambiente` > `R`).
3. Faça o upload da base de dados `Base2025.1.xlsx`.

---

## Observações

- A função `frequency_table()` foi definida para padronizar a geração de tabelas de frequência simples e relativa.
- Foram utilizados filtros e conversões para garantir o tratamento adequado de valores ausentes ou não informados.
- A análise foca em apresentar um panorama geral dos dados com foco em visualização e resumo estatístico.


---

## Colaboração

Este projeto foi desenvolvido em equipe com [João Ava](https://github.com/Joao-ava).
