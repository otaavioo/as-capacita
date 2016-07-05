# Índices

O objetivo deste pequeno pedaço do mundo do banco de dados é demonstrar na prática o quão importante são as definições de índices.
E não estou falando das chaves primárias de tabelas.

O funcionamento padrão do MySQL/MariaDB na hora de procurar dados leva em consideração as cláusulas WHERE, JOINS e ORDER BY. Quando procuramos por algo sem ter uma forma de organizar os dados de acordo com o tipo de pesquisa que estamos executando no momento, faz com que a procura leve muito tempo. Nós sabemos que ao procurar um nome na lista telefônica, podemos desconsiderar tudo antes da primeira letra do nome pesquisado. Com os índices o funcionamento é muito parecido.

Ao fazer uma pesquisa por clientes excluídos por exemplo em uma tabela de clientes, para encontrar todos os clientes que possuem aquela flag. Sem índice específico neste campo, o MySQL percorrerá todos os registros para ter certeza de que ele possuí todos os resultados.

Criando um índice para o "excluído" nesta tabela, nós estamos efetivamente criando uma "lista" separada (neste caso) para pesquisar apenas por este campo, tornando a pesquisa muito mais rápida por já sabermos quais são os registros que queremos e a probabilidade da consulta apenas percorrer os registros necessários é muito alta. Por exemplo se tivermos uma tabela com 5 mil registros de clientes, onde apenas 2 mil destes estão ativos. Ao pesquisar apenas os clientes ativos nós podemos utilizar este índice e internamente o MySQL percorrerá muito menos registros que os 5 mil, ou exatamente os 2 mil ativos ou um pouco mais (dependendo de como a paginação dos registros está em disco).

Nossa próxima seção é referente à PDO - PHP Data Objects e junto com esta seção veremos na prática como os índices podem nos ajudar.

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/MySQL/Relacionamentos.md#relacionamentos)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/MySQL/PDO_Indices.md)
