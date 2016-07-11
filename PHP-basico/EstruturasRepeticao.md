# Estruturas de repetição

### while

```php
<?php

$contador = 0;

while ($contador < 10) {
    echo $contador . '<br>';
    $contador++;
}

/*
0
1
2
3
4
5
6
7
8
9
*/

```

### do ... while

```php
<?php

$contador = 0;

do {
    echo $contador . '<br>';
    $contador++;
} while ($contador < 10);

/*
0
1
2
3
4
5
6
7
8
9
*/

```

### for

```php
<?php

for ($contador = 0; $contador < 10; $contador++) {
    echo $contador . '<br>';
}

/*
0
1
2
3
4
5
6
7
8
9
*/

```

### foreach

```php
<?php

$usuarios = ['Marvin', 'Trillian', 'Arthur'];

foreach ($usuarios as $usuario) {
    echo $usuario . '<br>';
}

/*
Marvin
Trillian
Arthur
*/

// ou

foreach ($usuarios as $indice => $usuario) {
    echo $indice . ': ' . $usuario . '<br>';
}

/*
0: Marvin
1: Trillian
2: Arthur
*/

```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/EstruturasCondicionais.md#estruturas-condicionais)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/Funcoes.md#fun%C3%A7%C3%B5es)
