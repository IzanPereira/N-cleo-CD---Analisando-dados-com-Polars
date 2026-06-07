# N-cleo-CD---Analisando-dados-com-Polars

# Analisando Dados de Vinhos com Polars

É uma Análise Exploratória de Dados (EDA) focado em processamento de alta performance utilizando a biblioteca **Polars** em Python. O projeto foi desenvolvido como parte das atividades de estruturação e manipulação de Dados o Núcleo CD do **DataLab**.

## Objetivo do Projeto
O objetivo principal deste script é explorar, limpar e extrair *insights* do dataset `winemag-data_first150k`, que contém avaliações, preços e origens de milhares de vinhos ao redor do mundo.

## Tecnologias Utilizadas
**Python 3.x**
**Polars** (Motor principal de processamento de dados)
https://docs.pola.rs/api/python/stable/reference/dataframe/index.html

## Estrutura do Pipeline de Dados

O script (`núcleo_cd_analisando_dados_com_polars.py`) está dividido nas seguintes etapas de processamento:

**Leitura e avaliação das colunas:**
Leitura do arquivo CSV (`pl.read_csv`).
Verificação de volumetria, metadados e tipagem das colunas (`shape()`, `dtypes()`, `glimpse()`, `describe()`).
Mapeamento de dados nulos (`null_count()`).

**Limpeza de Dados (Data Cleaning):**
Tratamento e remoção de valores ausentes para garantir a integridade das métricas (`drop_nulls()`).
Criando assim o dataset 'nova_wine'
Na limpeza na vi dificuldade, pois, a documentação do **Polars** é bem clara.

**Filtragem e Consultas Específicas:**
Extração de variedades únicas de vinhos produzidos no Brasil.
Filtros combinados de múltiplas condições lógicas (ex: Vinhos brasileiros com pontuação $\ge$ 85 e preço $<$ 20).
Identificação do vinho da uva Chardonnay com a nota máxima absoluta, nessa parte fiquei na dúvida se era para colocar o do agrupamento de todo o dataset, dai fiz os dois.

**Agrupamentos e Agregações (Group By & Agg):**
Cálculo do preço médio por país e por variedade de uva, ordenado em formato de *ranking*, nessa parte fiquei na dúvida se era para colocar o do agrupamento de todo o dataset, dai fiz os dois.
Cálculo da nota máxima atingida por cada variedade de vinho, nessa parte fiquei na dúvida se era para colocar o do agrupamento de todo o dataset, dai fiz os dois.

**Engenharia de Recursos (Feature Engineering):**
Criação de uma nova métrica calculada: **Custo-Benefício**, aqui não utilizei a `.insert_column`, pois, tive uma dificuldade quanto aos argumentos, dai optei por utilizando a operação `.with_columns()`.

## Como Executar

Certifique-se de ter o dataset `winemag-data_first150k.csv` no mesmo diretório do script.
Instale as dependências necessárias:
   ```bash
   pip install polars
```
``` Excute o script
   python núcleo_cd_analisando_dados_com_polars.py
```
O mesmo se encontra comentado, as respostas para as perguntas da atividade estão no código.
