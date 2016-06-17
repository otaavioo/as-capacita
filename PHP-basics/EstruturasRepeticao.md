# Estruturas de repetição

### while

```php
<?php

$contador = 0;

while ($contador < 10) {
    echo $contador, '<br>';
    $contador++;
}

?>
```

### do ... while

```php
<?php

$contador = 0;

do {
    echo $contador, '<br>';
    $contador++;
} while ($contador < 10);

?>
```

### for

```php
<?php

for ($contador = 0; $contador < 10; $contador++) {
    echo $contador, '<br>';
}

?>
```

### foreach

```php
<?php

$usuarios = ['Usuário 1', 'Usuário 2', 'Usuário 3'];

foreach ($usuarios as $usuario) {
    echo $usuario, '<br>';
}

// ou

foreach ($usuarios as $chave => $usuario) {
    echo $chave, ': ', $usuario, '<br>';
}

?>
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basics/EstruturasCondicionais.md#estruturas-condicionais)
|
[Início](https://github.com/agenciasys/as-capacita/blob/master/PHP-basics/README.md#php-b%C3%A1sico)
