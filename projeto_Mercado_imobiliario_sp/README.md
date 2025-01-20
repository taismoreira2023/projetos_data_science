# Projeto de Análise de Dados de Aluguéis de Imóveis em São Paulo

Este projeto realiza uma análise exploratória de dados sobre imóveis alugados na cidade de São Paulo. O conjunto de dados contém informações sobre imóveis disponíveis para locação, incluindo detalhes como endereço, tipo, área, número de quartos, garagem, aluguel e custo total.

## Objetivo

O objetivo principal deste projeto é analisar as variáveis do conjunto de dados e obter insights sobre o mercado de aluguel de imóveis em São Paulo, explorando tendências, correlações e comparações entre diferentes tipos de imóveis, bairros e características financeiras.

## Dados

O conjunto de dados contém as seguintes colunas:

- **address**: Localização completa da propriedade.
- **district**: Região onde o imóvel está situado.
- **area**: Tamanho do imóvel em metros quadrados (m²).
- **bedrooms**: Número de quartos disponíveis.
- **garage**: Total de vagas na garagem.
- **type**: Tipo de propriedade (apartamento, casa, etc.).
- **rent**: Valor do aluguel mensal.
- **total**: Soma do aluguel, impostos e outras taxas.

O arquivo foi lido usando a biblioteca `pandas`:

```python
import pandas as pd
df = pd.read_csv('data.csv', sep=',')
```

## Tratamento e Limpeza de Dados

Durante o processo de análise, foram realizados os seguintes tratamentos de dados:

- **Remoção de registros com área menor que 5 m²**, pois são considerados inválidos para a análise do mercado de aluguel de imóveis.
- **Remoção de registros com 0 quartos**, pois esses registros não faziam sentido para os tipos de imóveis analisados.
  
Os registros com valores ausentes ou inconsistentes foram tratados adequadamente, e o conjunto de dados foi verificado para garantir que não há valores nulos.

```python
df.isnull().sum()  # Verifica valores nulos
df.describe()  # Estatísticas descritivas
```

## Análise Exploratória

Diversas análises exploratórias foram realizadas, incluindo:

### Estatísticas Descritivas

- **Área média, mínima e máxima** dos imóveis.
- **Valor médio de aluguel** por tipo de imóvel.
- **Custo total médio** por bairro.

### Distribuição das Variáveis

- Distribuição do número de quartos (`bedrooms`).
- Quantidade de imóveis com garagem (`garage > 0`).
- Distribuição de imóveis por tipo e bairro.

### Correlações e Relações

- **Correlação entre o tamanho do imóvel (área) e o valor do aluguel (rent)**: foi identificada uma correlação positiva moderada (0.67).
  
```python
correlacao = df[['area','rent']].corr()
```

- **Análise do impacto da garagem no custo total**: imóveis com garagem tendem a ter um custo total mais alto.

### Comparação por Grupos

- **Comparação de aluguéis médios** por bairro, identificando os bairros mais caros e mais acessíveis.
- **Análise do custo total médio** por tipo de imóvel.

## Gráficos e Visualizações

Diversos gráficos foram gerados para auxiliar na visualização e interpretação dos dados:

- **Distribuição do número de quartos** nos imóveis.
- **Comparação do aluguel médio por tipo de imóvel**.
- **Top 15 bairros com maior custo total médio**.
- **Comparação de aluguéis médios nos bairros mais baratos e mais caros**.

### Exemplo de Gráfico de Aluguel Médio por Tipo de Imóvel

```python
plt.bar(categoria, valores, color='orange')
plt.title("Comparação do Aluguel Médio por Tipo de Imóvel")
```

## Insights Obtidos

- Imóveis maiores tendem a ter aluguéis mais altos.
- Bairros como **Alphaville** apresentam custos mais elevados, enquanto bairros como **Jardim Jaçanã** possuem aluguéis mais acessíveis.
- Imóveis com garagem têm custos totais significativamente mais altos em comparação com os imóveis sem garagem.

## Conclusões

Este projeto oferece uma análise detalhada do mercado de aluguel de imóveis em São Paulo, permitindo que se identifiquem tendências de preço, preferências de bairro e características dos imóveis que influenciam o valor do aluguel. A análise pode ser útil para corretores de imóveis, inquilinos e investidores que buscam entender melhor o mercado de aluguel na cidade.

## Tecnologias Utilizadas

- **Pandas**: Manipulação e análise de dados.
- **Matplotlib**: Visualização de dados.
- **Seaborn**: Visualização de dados com foco em gráficos estatísticos.

## Como Rodar o Projeto

1. Clone o repositório.
2. Instale as dependências:

```bash
pip install pandas matplotlib seaborn
```

3. Execute o script para carregar os dados e realizar a análise.

```python
python analise_imoveis.py
```
