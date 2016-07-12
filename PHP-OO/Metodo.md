# Método

```php
<?php

class Usuario
{
    public $id;
	public $nome;
    public $email;

    public function setId($id)
    {
        $this->id = $id;
    }
	
	public function setNome($nome)
    {
        $this->nome = $nome;
    }

    public function setEmail($email)
    {
        $this->email = $email;
    }

    public function getId()
    {
        return $this->id;
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

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Objeto.md#objeto)
|
[Próximo >>](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Objeto2.md#objeto)
