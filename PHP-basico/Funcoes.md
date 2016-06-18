# Funções

```php
<?php

function exibe()
{
    echo 'Olá mundo!';
}

exibe();

```

### Passagem de parâmetros

```php
<?php

function exibe($frase)
{
    echo $frase;
}

exibe('Olá mundo!');
```

### Mais de um parâmetro

```php
<?php

function exibe($palavra1, $palavra2)
{
    echo $palavra1, ' ', $palavra2;
}

exibe('Olá', 'mundo!');
```

### Funções que retornam valor.

```php
<?php

function exibe()
{
    return 'Olá mundo!';
}

echo exibe();

// ou

$valor = exibe();
echo $valor;

```

### Passagem de parâmetros

```php
<?php

function exibe($frase)
{
    return $frase;
}

echo exibe('Olá mundo!');

// ou

$valor = exibe('Olá mundo!');
echo $valor;
```

### Mais de um parâmetro

```php
<?php

function exibe($palavra1, $palavra2)
{
    echo $palavra1, ' ', $palavra2;
}

exibe('Olá', 'mundo!');

```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/EstruturasCondicionais.md#estruturas-condicionais)
|
[Início](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/README.md#php-b%C3%A1sico)
