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
$usuario->nome = 'Nome do usuário';

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
$admin->setNome('Nome do Admin');

$usuario = new Usuario();
$usuario->setNome('Nome do Usuário');

echo 'Admin: ' . $admin->getNome();
echo 'Usuário: ' . $usuario->getNome();
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
$admin->setNome('Nome do Admin');
$admin->setSenha(123);

$usuario = new Usuario();
$usuario->setNome('Nome do Usuário');

echo 'Admin: ' . $admin->getNome();
echo 'Senha: ' . $admin->getSenha();
echo 'Usuário: ' . $usuario->getNome();
```
