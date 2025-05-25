# Analise_Imobiliaria
Estudando sobre Análise de Dados usando Python

# Relatório de Análise de Dados de Imóveis para Aluguel

## 1. Introdução

Este relatório documenta as etapas e descobertas de um projeto de análise exploratória e tratamento de dados de um conjunto de dados de imóveis para aluguel. O objetivo principal foi entender as características da base de dados, realizar análises exploratórias para obter insights, limpar e filtrar os dados para análises específicas e preparar os dados para uso futuro.

## 2. Fonte de Dados

Os dados utilizados neste projeto foram obtidos de:

*   **URL:** `https://raw.githubusercontent.com/alura-cursos/pandas-conhecendo-a-biblioteca/main/base-de-dados/aluguel.csv`
*   **Descrição:** O conjunto de dados contém informações sobre diversos imóveis, incluindo tipo, bairro, número de quartos, valor do aluguel, condomínio, IPTU, entre outros.

## 3. Preparação e Carregamento dos Dados

A primeira etapa consistiu em carregar os dados utilizando a biblioteca pandas. Foi necessário identificar o separador correto do arquivo CSV (ponto e vírgula) para garantir a leitura adequada dos dados.

Foram realizadas verificações iniciais para entender a estrutura do DataFrame, como:

*   Exibição das primeiras e últimas linhas (`head()`, `tail()`)
*   Verificação do tipo da variável (`type()`)
*   Obtenção das dimensões do DataFrame (`shape`)
*   Listagem dos nomes das colunas (`columns`)
*   Obtenção de informações gerais sobre os dados (`info()`)

## 4. Análise Exploratória de Dados (AED)

A análise exploratória teve como foco inicial entender a distribuição e características dos dados.

### 4.1. Valor Médio de Aluguel por Tipo de Imóvel

Foi calculada a média do valor de aluguel agrupando por tipo de imóvel para identificar a variação de preço entre diferentes categorias.

Foi gerado um gráfico para visualiza o valor médio de aluguel para cada tipo de imóvel, ordenado do menor para o maior valor.

### 4.2. Removendo Imóveis Comerciais

Para focar a análise em imóveis residenciais, foi criada uma lista de tipos de imóveis comerciais e estes foram removidos da base de dados.

### 4.3. Percentual de Cada Tipo de Imóvel (Residenciais)

Após a remoção dos imóveis comerciais, foi analisado o percentual de cada tipo de imóvel restante na base.

Foi gerado um gráfico de barras mostra a proporção de cada tipo de imóvel residencial no conjunto de dados filtrado.

### 4.4. Selecionando Apenas Apartamentos

Para análises mais detalhadas, o DataFrame foi filtrado para conter apenas imóveis do tipo "Apartamento".

## 5. Tratamento e Filtragem dos Dados

Esta seção detalha o processo de limpeza e filtragem dos dados focando nos apartamentos.

### 5.1. Lidando com Dados Nulos

Foi verificada a presença de dados nulos e estes foram preenchidos com o valor 0.

### 5.2. Removendo Registros Inconsistentes

Foram removidos os registros onde o valor do Condomínio ou do Aluguel eram iguais a 0, pois são considerados inconsistentes para a análise de imóveis alugados.

### 5.3. Remoção da Coluna 'Tipo'

Após filtrar o DataFrame para conter apenas apartamentos, a coluna 'Tipo' se tornou redundante e foi removida.

### 5.4. Aplicação de Filtros Específicos

Foram aplicados dois filtros para criar subconjuntos de dados para análises específicas:

*   **Filtro 1:** Apartamentos com 1 quarto e aluguel menor que R$ 1200.
*   **Filtro 2:** Apartamentos com pelo menos 2 quartos, aluguel menor que R$ 3000 e área maior que 70 m².

## 6. Manipulação dos Dados

Novas colunas foram criadas para enriquecer a base de dados.

### 6.1. Criando Colunas Numéricas

Foram criadas colunas para o valor total por mês (Valor + Condomínio) e valor total por ano (Valor por Mês * 12 + IPTU).

### 6.2. Criando Colunas Categóricas

Foi criada uma coluna de descrição detalhada do imóvel e uma coluna indicando se o imóvel possui suíte.

## 7. Salvando os Dados

Os DataFrames processados e filtrados foram salvos em arquivos CSV para uso futuro.

## 8. Conclusões

Este projeto permitiu uma análise inicial do conjunto de dados de imóveis para aluguel. Foram identificadas e tratadas inconsistências, e a base foi preparada para análises mais aprofundadas, com foco específico em apartamentos. A criação de novas colunas numéricas e categóricas enriqueceu o conjunto de dados para futuros estudos.

