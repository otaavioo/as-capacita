# Modificadores de acesso

## public

Acessível de todos os lugares em que for chamado utilizando o objeto ou a classe.

```php
<?php

class Usuario
{
    public $nome;
}

$usuario = new Usuario();
$usuario->nome = 'Marvin';

echo 'Usuário: ' . $usuario->nome;
```

## protected

Acessível apenas dentro da classe que o define ou dentro das classes que herdam comportamento.

```php
<?php

class Usuario 
{
    protected $nome;

    public function setNome($nome)
    {
        $this->nome = $nome;
    }

    public function getNome()
    {
        return $this->nome;
    }
}

class Admin extends Usuario 
{

}

$admin = new Admin();
$admin->setNome('Arthur');

$usuario = new Usuario();
$usuario->setNome('Marvin');

echo 'Admin: ' . $admin->getNome() . '<br>';
echo 'Usuário: ' . $usuario->getNome() . '<br>';
```

## private

Acessível apenas dentro da classe que o define.

```php
<?php

class Usuario
{
    private $nome;

    public function setNome($nome)
    {
        $this->nome = $nome;
    }

    public function getNome()
    {
        return $this->nome;
    }
}

class Admin extends Usuario
{
    private $senha;

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
$admin->setNome('Arthur');
$admin->setSenha(123);

$usuario = new Usuario();
$usuario->setNome('Marvin');

echo 'Admin: ' . $admin->getNome() . '<br>';
echo 'Senha: ' . $admin->getSenha() . '<br>';
echo 'Usuário: ' . $usuario->getNome() . '<br>';
```

[<< Anterior](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/Heranca.md#heran%C3%A7a)
|
[Próximo](https://github.com/agenciasys/as-capacita/blob/master/PHP-OO/README.md#php-oo)
