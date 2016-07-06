# Normalização

Temos atualmente 5 formas de normalização. Falaremos apenas sobre as 3 principais, estas darão sentido ao nosso banco de dados.


**1FN – Primeira Forma Normal**

Uma tabel só estará na 1FN se todos os seus atributos/colunas não forem de dados repetitivos ou colunas que tenham mais de um valor (usando-se separadores por exemplo).

Passos para aplicar a 1FN:

1. Identificação da chave primária da tabela
2. Identificação da(s) coluna(s) que contem dados repetidos e removê-la(s).
3. Criação de nova(s) tabela(s) com chave primária para armazenamento do(s) dado(s) repetido(s).
4. Criar uma relação entre a tabela principal e a(s) tabela(s) secundária(s)

Exemplo:

Tabela: Fornecedores

| iFornecedorId  | sFornecedorNome  |  sFornecedorEndereco   |    sFornecedorTelefone    |
| -------------- |:----------------:|:----------------------:|:-------------------------:|
| 1              | Fornecedor 1     |  Rua xxx, 256          | 47 34330000               |
| 2              | Fornecedor 2     |  Rua yyy, 777          | 96758585                  |
| 3              | Fornecedor 3     |  Rua zzz, 123          | 11 23456789 / 48 98899898 |


Após a 1FN


Tabela: Fornecedores

| iFornecedorId  | sFornecedorNome  |  sFornecedorEndereco   |
| -------------- |:----------------:|:----------------------:|
| 1              | Fornecedor 1     |  Rua xxx, 256          |
| 2              | Fornecedor 2     |  Rua yyy, 777          |
| 3              | Fornecedor 3     |  Rua zzz, 123          |


Tabela: FornecedoresTelefones

| iFornecedorTelefoneId  | iFornecedorId  |  sFornecedorTelefone |
| ---------------------- |:--------------:|:--------------------:|
| 1                      | 1              |  47 34330000         |
| 2                      | 2              |  96758585            |
| 3                      | 3              |  11 23456789         |
| 4                      | 3              |  48 98899898         |


**2FN – Segunda Forma Normal**

Uma tabela só estará na 2FN se estiver na 1FN e se todos os seus atributos/colunas não chaves dependam apenas da chave primária. Caso algum atributo dependa de apenas uma parte da chave primária, isso é considerada uma violação da 2FN.

Passos para aplicar a 2FN:

1. Identificar a(s) coluna(s) que não é(são) dependente(s) da chave primária.
2. Remover a(s) coluna(s) e criar nova(s) tabela(s) com esses dados.

Exemplo:

Tabela: Orcamentos

| iOrcamentoId | dtDataOrcamento | iProdutoId |  sProdutoNome    |  iQtd   | dcValorUnitario | dcValorTotal |
| ------------ |:---------------:|:----------:|:----------------:|:-------:|:---------------:|:------------:|
| 1            | 2016-05-15      | 123        | Câmera Digital   |  1      |  500.00         | 500.00       |
| 2            | 2016-05-19      | 124        | Cartão SD (16GB) |  2      |  50.00          | 100.00       |
| 3            | 2016-06-27      | 136        | Filtro UV        |  3      |  89.90          | 269.70       |
| 4            | 2016-06-05      | 123        | Câmera Digital   |  1      |  500.00         | 500.00       |
| 5            | 2016-06-23      | 136        | Filtro UV        |  2      |  89.90          | 179.80       |

Após a 2FN

Tabela: Orcamentos

| iOrcamentoId | dtDataOrcamento | iProdutoId | iQtd   | dcValorUnitario | dcValorTotal |
| ------------ |:---------------:|:----------:|:------:|:---------------:|:------------:|
| 1            | 2016-05-15      | 123        | 1      |  500.00         | 500.00       |
| 2            | 2016-05-19      | 124        | 2      |  50.00          | 100.00       |
| 3            | 2016-06-27      | 136        | 3      |  89.90          | 269.70       |
| 4            | 2016-06-05      | 123        | 1      |  500.00         | 500.00       |
| 5            | 2016-06-23      | 136        | 2      |  89.90          | 179.80       |


Tabela: Produtos

| iProdutoId | sProdutoNome       |
| ------------ |:----------------:|
| 123          | Câmera Digital   |
| 124          | Cartão SD (16GB) |
| 136          | Filtro UV        |


**3FN – Terceira Forma Normal**

Uma tabela só estará na 3FN se estiver na 2FN e se todos os atributos/colunas não chave forem independentes e todos dependem apenas da chave primária.

Passos para aplicar a 3FN:

1. Identificar quais colunas são dependentes de outras colunas não chave.
2. Removê-las.

Exemplo:

Tabela: Orcamentos

| iOrcamentoId | dtDataOrcamento | iProdutoId | iQtd   | dcValorUnitario | dcValorTotal |
| ------------ |:---------------:|:----------:|:------:|:---------------:|:------------:|
| 1            | 2016-05-15      | 123        | 1      |  500.00         | 500.00       |
| 2            | 2016-05-19      | 124        | 2      |  50.00          | 100.00       |
| 3            | 2016-06-27      | 136        | 3      |  89.90          | 269.70       |
| 4            | 2016-06-05      | 123        | 1      |  500.00         | 500.00       |
| 5            | 2016-06-23      | 136        | 2      |  89.90          | 179.80       |

Após a 3FN

Tabela: Orcamentos

| iOrcamentoId | dtDataOrcamento | iProdutoId | iQtd   | dcValorUnitario |
| ------------ |:---------------:|:----------:|:------:|:---------------:|
| 1            | 2016-05-15      | 123        | 1      |  500.00         |
| 2            | 2016-05-19      | 124        | 2      |  50.00          |
| 3            | 2016-06-27      | 136        | 3      |  89.90          |
| 4            | 2016-06-05      | 123        | 1      |  500.00         |
| 5            | 2016-06-23      | 136        | 2      |  89.90          |


[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/MySQL/README.md#mysql---normaliza%C3%A7%C3%A3o-relacionamentos-e-%C3%8Dndices)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/MySQL/Relacionamentos.md#relacionamentos)
