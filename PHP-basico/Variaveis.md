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

var_dump($fruta); 
// string(7) "abacate" 
```

### int

```php
<?php

$numero = 5;

var_dump($numero); 
// int(5)
```

### float

```php
<?php

$numero = 5.3; 

var_dump($numero); 
// float(5.3)

```

### boolean (`true` e `false`)

```php
<?php

$bool = true;

var_dump($bool); 
// bool(true) 

// ou

$bool = false;

var_dump($bool); 
// bool(false) 

```

### array

```php
<?php

$frutas = ['maçã', 'banana', 'laranja']; 

var_dump($frutas);
// array(3) { [0]=> string(6) "maçã" [1]=> string(6) "banana" [2]=> string(7) "laranja" }

```

### array associativo

```php
<?php

$usuario = [
    'id' => 1,
    'nome' => 'Nome do usuário',
    'email' => 'emaildousuario@dominio.com',
];

var_dump($usuario);
// array(3) { ["id"]=> int(1) ["nome"]=> string(16) "Nome do usuário" ["email"]=> string(26) "emaildousuario@dominio.com" } 

```

Definindo um array para preencher depois.

```php
<?php

$frutas = [];
$frutas[] = 'maçã';
$frutas[] = 'banana';
$frutas[] = 'laranja';

$usuario = [];
$usuario['id'] = 1;
$usuario['nome'] = 'Nome do usuário';
$usuario['email'] = 'emaildousuario@dominio.com';

```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/Comentarios.md#comentários)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/EstruturasCondicionais.md#estruturas-condicionais)
