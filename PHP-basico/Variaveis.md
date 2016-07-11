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

$numero = 42;

var_dump($numero); 
// int(42)
```

### float

```php
<?php

$numero = 4.2; 

var_dump($numero); 
// float(4.2)

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

$usuarios = ['Marvin', 'Trillian', 'Arthur']; 

var_dump($usuarios);
// array(3) { [0]=> string(6) "Marvin" [1]=> string(8) "Trillian" [2]=> string(6) "Arthur" } 

echo $usuarios[1];

```

### array associativo

```php
<?php

$usuario = [
    'id' => 1,
    'nome' => 'Marvin',
    'email' => 'marvin@gmail.com',
];

var_dump($usuario);
// array(3) { ["id"]=> int(1) ["nome"]=> string(6) "Marvin" ["email"]=> string(16) "marvin@gmail.com" } 

```

Definindo um array para preencher depois.

```php
<?php

$usuario = [];
$usuario[] = 1;
$usuario[] = 'Marvin';
$usuario[] = 'marvin@gmail.com';

var_dump($usuario);
// array(3) { [0]=> int(1) [1]=> string(6) "Marvin" [2]=> string(18) "marvin@gmail.com" }
```

Acesso

```php
echo $usuario[1];
// Marvin
```

```php
$usuario = [];
$usuario['id'] = 1;
$usuario['nome'] = 'Marvin';
$usuario['email'] = 'marvin@gmail.com';

var_dump($usuario);
// array(3) { ["id"]=> int(1) ["nome"]=> string(6) "Marvin" ["email"]=> string(18) "marvin@gmail.com" } 

```

Acesso

Acesso

```php
echo $usuario['nome'];
// Marvin
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/Comentarios.md#comentários)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-basico/EstruturasCondicionais.md#estruturas-condicionais)
