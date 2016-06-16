# Variáveis

- Nomes de variáveis devem começar com `$`.
- Nomes de variáveis não podem começar com números.
- Nomes de variáveis não podem conter espaços.

### string

```php
<?php

$fruta = 'abacate';

// ou

$fruta = "abacate";
?>
```

### int

```php
<?php

$numeroInteiro = 5;

?>
```

### float

```php
<?php

$pontoFlutuante = 5.3;

?>
```

### boolean (`true` e `false`)

```php
<?php

$bool = true;

// ou

$bool = false;

?>
```

### array

```php
<?php

$frutas = ['maçã', 'banana', 'laranja'];

?>
```

### array associativo

```php
<?php

$usuario = [
    'id' => 1,
    'nome' => 'Nome do usuário',
    'email' => 'emaildousuario@dominio.com',
];

// Definindo como array e depois preenchendo.

$frutas = [];
$frutas[] = 'maçã';
$frutas[] = 'banana';
$frutas[] = 'laranja';

$usuario = [];
$usuario['id'] = 1;
$usuario['nome'] = 'Nome do usuário';
$usuario['email'] = 'emaildousuario@dominio.com';

?>
```
