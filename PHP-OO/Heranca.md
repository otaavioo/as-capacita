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
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Objeto2.md#objeto)
|
[Próximo >>](#)
