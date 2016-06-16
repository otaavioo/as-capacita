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

?>
```

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

?>
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basics/Variaveis.md)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-basics/EstruturasRepeticao.md)
