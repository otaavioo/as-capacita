# Método

```php
<?php

class Usuario
{
    public $nome;
    public $email;
    
    public function setNome($nome)
    {
        $this->nome = $nome;
    }

    public function setEmail($email)
    {
        $this->email = $email;
    }

    public function getNome()
    {
        return $this->nome;
    }

    public function getEmail()
    {
        return $this->email;
    }
}
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Atributo.md#atributo)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Objeto.md#objeto)
