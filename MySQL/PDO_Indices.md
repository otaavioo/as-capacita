# PDO e Exemplo de Índice

Primeiramente vamos abrir o phpMyAdmin de vocês para facilitar todo o processo.

Criem também uma pasta chamada **pdo-indices** no diretório dispónível pro servidor web. Iremos utilizar o PHP para criar registros randômicos em tabelas e ciraremos um índice para perquisarmos.

Acessando o seu phpMyAdmin, cliquem na aba SQL e digitem o seguinte conteúdo:

    CREATE DATABASE as_capacita_indexes;
    USE as_capacita_indexes;

Executem estes comandos (apertando CTRL+Enter ou clicando no botão).

Estes comandos servem para criar o banco de dados e selecionar ele para as próximas querys digitadas ali no phpMyAdmin.

Agora criaremos duas tabelas que terão os mesmos dados. A diferença é que uma delas teremos índices e na outra não.

    CREATE TABLE agenda (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    ddd INT(3) NOT NULL,
    numero INT(8) NOT NULL,
    excluido INT(1) NOT NULL DEFAULT 0
    ) ENGINE=InnoDB;

    CREATE TABLE agenda_indexada (
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    ddd INT(3) NOT NULL,
    numero INT(8) NOT NULL,
    excluido INT(1) NOT NULL DEFAULT 0
    ) ENGINE=InnoDB;


Agora criem um arquivo **index.php** na pasta **pdo-indices**. Abaixo o conteúdo que será digitado neste arquivo. Aqui iremos utilizar a lib PDO para nos auxiliar a inserir muitos registros de uma vez só.

Para consulta: PHP Data Objects -  <http://php.net/manual/pt_BR/book.pdo.php>

```php
$db = new PDO('mysql:host=localhost;dbname=as_capacita_indexes', 'root', 'admin') or die("Erro");

$sql = "INSERT INTO agenda (ddd, numero, excluido) VALUES ";

for($i = 0; $i < 10000; $i++){
    $sql .= "
    (:ddd$i, :numero$i, :excluido$i), ";
}

$sql = substr($sql, 0 , -2).";";

try {
    $stmt = $db->prepare($sql);

    for($i = 0; $i < 10000; $i++){
        $ddd = rand(10,99);
        $numero = rand(1000,9999).rand(1000,9999);
        $excluido = rand(0,1);

        $stmt->bindValue(":ddd$i", $ddd);
        $stmt->bindValue(":numero$i", $numero);
        $stmt->bindValue(":excluido$i", $excluido);
    }

    try {
        $stmt->execute();
    } catch (Exception $e) {
        $stmt->debugDumpParams();
        echo "Código: 1 <br /> <pre>";
        print_r($e);
        exit();
    }

} catch (Exception $e) {
    echo "Código: 2 <br /> <pre>";
    print_r($e);
    exit();
}
echo "<br />Script finalizado! <br />";

```

Agora podemos criar os índices que desejamos.

**A Escolha de Índices**

Índices devem ser criados em colunas que usamos para pesquisa,
ordenação ou agrupamento. Nunca em colunas que só são exibidas. Em
outras palavras, as colunas candidatas são aquelas que aparecem na
cláusula WHERE, joins, ORDER BY ou GROUP BY.

Iremos criar dois índices, um para o campo numero e outro para o campo excluido. Para isto abram o phpMyAdmin novamente, na aba SQL do banco de dados as_capacita_indexes e executem o conteúdo abaixo.

    CREATE INDEX numero on agenda_indexada(numero(4));
    # apenas os 4 primeiros digitos (deixa mais rápida a atualização de inserts e updates)

    CREATE INDEX excluido on agenda_indexada(excluido);
    # vai dividir a tabela entre ativos ou excluídos

Nossos próximos passos são fazer as pesquisas sem índices primeiro e depois a mesma consulta com os índices para isto utilizaremos exclusivamente o phpMyAdmin.

Primeiramente vamos pegar alguns registros exemplo para consulta.  abaixo exemplos de consultas que podemos executar e ver claramente o resultado.

    SELECT SQL_NO_CACHE * FROM agenda WHERE ddd = 22 AND numero = 43117459;

    SELECT SQL_NO_CACHE * FROM agenda WHERE numero = 43117459 LIMIT 5;

    SELECT SQL_NO_CACHE * FROM agenda WHERE excluido = 1 LIMIT 500;

**Comando mágico...**

Para auxiliar na criação de índices é muito interessante o uso do comando **EXPLAIN**.

    EXPLAIN SELECT SQL_NO_CACHE * FROM agenda WHERE ddd = 22 AND numero = 43117459;

    EXPLAIN SELECT SQL_NO_CACHE * FROM agenda WHERE excluido = 1 LIMIT 500;

Com o retorno do **EXPLAIN** nós conseguimos ver quais chaves estão sendo usadas ou não, quantos registros são percorridos em cada tabela (no caso de JOINS). Realmente é um comando muito interessante, u é utilizado para validar se a chave criada é a ideal, ou se ela afetou outra consulta negativamente pois criar índices pode ter impacto negativo em outras consultas. É ideal sempre testar todas as consultas que são executadas nas tabelas onde foram criados os índices, para garantir a qualidade e velocidade.

Espero com essa pequena aula vocês considerem a importância da definição de índices para a performance de um sistema. E não apenas para um sistema, mas também para o setor de infra. Menos carga em cada consulta no servidor de banco de dados se traduz em redução de custos de infra ou aumento de número de respostas/usuários com a mesma configuração, permitindo manter o mesmo servidor por muito mais tempo sem ter que aumentar configurações (RAM/CPU).

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/MySQL/Indices.md)
|
[Início](https://github.com/agenciasys/as-capacita/blob/master/MySQL/README.md#mysql---normaliza%C3%A7%C3%A3o-relacionamentos-e-%C3%8Dndices)
