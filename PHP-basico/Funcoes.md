# Funções

```php
<?php

function exibir()
{
    echo 'Olá mundo!';
}

exibir();

```

### Passagem de parâmetros

```php
<?php

function exibir($frase)
{
    echo $frase;
}

exibir('Olá mundo!');
```

### Mais de um parâmetro

```php
<?php

function exibir($palavra1, $palavra2)
{
    echo $palavra1, ' ', $palavra2;
}

exibir('Olá', 'mundo!');
```

### Funções que retornam valor

```php
<?php

function exibir()
{
    return 'Olá mundo!';
}

echo exibir();

// ou

$valor = exibir();
echo $valor;

```

### Passagem de parâmetros

```php
<?php

function exibir($frase)
{
    return $frase;
}

echo exibir('Olá mundo!');

// ou

$valor = exibir('Olá mundo!');
echo $valor;
```

### Mais de um parâmetro

```php
<?php

function exibir($palavra1, $palavra2)
{
    return $palavra1, ' ', $palavra2;
}

exibir('Olá', 'mundo!');

```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/EstruturasRepeticao.md#estruturas-de-repeti%C3%A7%C3%A3o)
|
[Início](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/README.md#php-b%C3%A1sico)
