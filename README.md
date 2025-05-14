# Análise de Dados de Funcionários com Pandas e Matplotlib

Este script Python utiliza as bibliotecas Pandas e Matplotlib para realizar uma análise básica de um conjunto de dados de funcionários armazenado em um arquivo CSV chamado `funcionarios.csv`.

## Bibliotecas Utilizadas

* **Pandas:** Utilizada para manipulação e análise de dados, fornecendo estruturas de dados como DataFrames.
* **Matplotlib:** Utilizada para criação de gráficos e visualizações de dados.

## Carregamento e Inspeção dos Dados

1.  **Importação das bibliotecas:**
    ```python
    import pandas as pd
    import matplotlib.pyplot as plt
    ```
    As bibliotecas Pandas e Matplotlib são importadas para serem utilizadas no script.

2.  **Carregamento do arquivo CSV:**
    ```python
    df = pd.read_csv('funcionarios.csv')
    ```
    A função `pd.read_csv()` do Pandas é utilizada para ler o conteúdo do arquivo `funcionarios.csv` e armazená-lo em um DataFrame chamado `df`.

3.  **Visualização das primeiras linhas:**
    ```python
    df.head()
    ```
    O método `head()` exibe as 5 primeiras linhas do DataFrame `df`, fornecendo uma visão inicial dos dados.

4.  **Verificação dos tipos de dados:**
    ```python
    df.dtypes
    ```
    O atributo `dtypes` retorna o tipo de dados de cada coluna no DataFrame, auxiliando na compreensão da natureza de cada variável.

5.  **Visualização das últimas linhas:**
    ```python
    df.tail()
    ```
    O método `tail()` exibe as 5 últimas linhas do DataFrame `df`.

## Filtragem de Dados

1.  **Seleção de funcionários com idade superior a 30 anos:**
    ```python
    df[df['idade'] > 30]
    ```
    Esta linha utiliza indexação booleana para selecionar e exibir apenas as linhas do DataFrame onde o valor da coluna 'idade' é maior que 30.

2.  **Seleção de funcionários com salário superior a 5000:**
    ```python
    df[df['salário'] > 5000]
    ```
    Similar ao exemplo anterior, esta linha filtra o DataFrame para mostrar apenas os funcionários cujo 'salário' é maior que 5000.

3.  **Seleção de funcionários com idade superior a 30 anos E salário superior a 5000:**
    ```python
    maiorTrinta = df['idade'] > 30
    salarioCincoK = df['salário'] > 5000
    df[maiorTrinta & salarioCincoK]
    ```
    Aqui, duas séries booleanas (`maiorTrinta` e `salarioCincoK`) são criadas representando as condições. O operador `&` (AND) combina essas condições, e o resultado é usado para filtrar o DataFrame, exibindo apenas os funcionários que atendem a ambas as condições.

## Criação e Remoção de Colunas

1.  **Criação da coluna 'salário anual':**
    ```python
    df['salário anual'] = df['salário'] * 12
    df
    ```
    Uma nova coluna chamada 'salário anual' é criada no DataFrame. Os valores desta coluna são calculados multiplicando os valores da coluna 'salário' por 12. O DataFrame resultante com a nova coluna é então exibido.

2.  **Remoção da coluna 'salário anual':**
    ```python
    df = df.drop('salário anual', axis=1)
    df
    ```
    O método `drop()` é utilizado para remover a coluna 'salário anual' do DataFrame. O argumento `axis=1` especifica que uma coluna deve ser removida (ao invés de uma linha). O DataFrame atualizado, sem a coluna 'salário anual', é então exibido.

## Informações do DataFrame

```python
df.info()

O método info() fornece um resumo conciso do DataFrame, incluindo o número total de entradas, o tipo de dados de cada coluna e a quantidade de valores não nulos.
Visualização dos Dados
Python

plt.figure(figsize=(12, 6))
plt.bar(df['nome'], df['salário'], color='skyblue')
plt.xticks(rotation=45, ha='right')
plt.title('Salário por Funcionário')
plt.xlabel('Nome')
plt.ylabel('Salário (R$)')
plt.tight_layout()
plt.show()

Esta seção utiliza a biblioteca Matplotlib para criar um gráfico de barras visualizando o salário de cada funcionário.

    Criação da figura e definição do tamanho:
    Python

plt.figure(figsize=(12, 6))

plt.figure() cria uma nova figura para o gráfico, e figsize define a largura e a altura da figura em polegadas.

Criação do gráfico de barras:
Python

plt.bar(df['nome'], df['salário'], color='skyblue')

A função plt.bar() cria o gráfico de barras. A coluna 'nome' é utilizada para as barras no eixo x, e a coluna 'salário' define a altura das barras. A cor das barras é definida como 'skyblue'.

Rotação dos rótulos do eixo x:
Python

plt.xticks(rotation=45, ha='right')

plt.xticks() ajusta os rótulos do eixo x. rotation=45 inclina os rótulos em 45 graus para evitar sobreposição, e ha='right' alinha os rótulos à direita.

Definição do título do gráfico:
Python

plt.title('Salário por Funcionário')

plt.title() define o título que será exibido no topo do gráfico.

Definição do rótulo do eixo x:
Python

plt.xlabel('Nome')

plt.xlabel() define o rótulo do eixo x.

Definição do rótulo do eixo y:
Python

plt.ylabel('Salário (R$)')

plt.ylabel() define o rótulo do eixo y, indicando a unidade da variável ('R$' para Real brasileiro).

Ajuste do layout para evitar cortes:
Python

plt.tight_layout()

plt.tight_layout() ajusta automaticamente o espaçamento entre os elementos do gráfico para garantir que tudo se encaixe corretamente e os rótulos não sejam cortados.

Exibição do gráfico:
Python

plt.show()

plt.show() exibe o gráfico gerado.