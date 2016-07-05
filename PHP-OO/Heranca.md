# Herança

Em orientação a objetos, a herança pode ser implementada com a palavra chave `extends`

```php
<?php

class Admin extends Usuario
{
    public $senha;
    
    public function setSenha($senha)
    {
        $this->senha = $senha;
    }

    public function getSenha()
    {
        return $this->senha;
    }
}

$admin = new Admin();

$admin->setNome('Nome do admin');
$admin->setEmail('email@dominio.com');
$admin->setSenha(123);
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Objeto2.md#objeto)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/ModificadoresAcesso.md#public)
