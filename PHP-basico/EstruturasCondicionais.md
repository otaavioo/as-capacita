# Estruturas condicionais

### if ... else

```php
<?php

$numero = 5;

if ($numero > 5) {
    echo 'O número é maior que 5';
} else if ($numero < 5) {
    echo 'O número é menor que 5';
} else {
    echo 'O número é igual a 5';
}

```

### Aplicando um pouco de cleancode...

```php
<?php

$numero = 5;
$mensagem = 'O número é igual a 5';

if ($numero > 5) {
    $mensagem = 'O número é maior que 5';
}

if ($numero < 5) {
    $mensagem = 'O número é menor que 5';
}

echo $mensagem;
```

> Existe também a notação curta, com delimitadores `:` (dois pontos).

### switch ... case

```php
<?php

$numero = 3;

switch ($numero) {
    case 1:
        echo 'O número é 1';
        break;
    case 2:
        echo 'O número é 2';
        break;
    default:
        echo 'O número é 3';
}

```

### Ternário

```php
<?php

$numero = 5;

$resposta = ($numero > 5) ? 'Maior que 5' : 'Menor ou igual a 5';

```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/Variaveis.md#variáveis)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/EstruturasRepeticao.md#estruturas-de-repetição)
