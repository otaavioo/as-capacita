# Phalcon

[Menu principal](https://github.com/agenciasys/as-capacita/blob/master/README.md#as-capacita)

1. Lançado em 2012, é um framework open source(código aberto)
2. Contem bibliotecas para todas as funcionalidades necessárias para escrever uma aplicação completa
3. Sua documentação já foi traduzido para, pelo menos, 14 idiomas (inclusive português) [link](https://docs.phalconphp.com/pt/)
4. Escrito em C, roda como um extensão do PHP (não fica preso às limitaçẽos do PHP, atendendo a um número muito maior de requisições que os seus concorrentes ![Performance](http://blog.umbler.com/wp-content/uploads/2016/06/Phalcon-1.png)
5. É considerado o framework PHP mais rápido disponível no mercado [link](http://blog.umbler.com/wp-content/uploads/2016/06/Phalcon-2.png)
6. Citação: "Uma grande desvantagem para o PHP é que em cada solicitação, todos os arquivos são lidos a partir do disco rígido, traduzidos, e então executados. Isso ocasiona uma perda de desempenho importante quando comparado com outras linguagens como Ruby (Rails) ou Python (Django). Com Phalcon, todo o framework já está em memória, não havendo a necessidade de processar todos os arquivos."
7. Curva de aprendizado menor, pela sua similaridade ao PHP nativo
8. Benchmark [link](https://docs.phalconphp.com/en/1.2.6/reference/benchmark/hello-world.html)
8. [Documentação oficial do PHP](http://php.net/)

# MVC

MVC é um padrão de arquitetura de software que separa a informação (e as suas regras de negócio) da interface com a qual o usuário interage.
É uma forma de estruturar seu projeto/aplicação de forma que a interface de interação (view) esteja separada do controle da informação em si (models), separação essa que é intermediada por uma outra camada controladora (controllers).

Model (ou modelo)
O model é a camada que representa os seus dados, provendo meios de acesso (leitura e escrita) à esses dados.

Controller (ou controlador)
No controller você tem métodos públicos que são chamados de actions, cada action é responsável por uma “página” do seu site/sistema. É o controller quem decide:
Qual model usar;
Quais pedidos fazer pro model;
Qual combinação de views será usada para exibir os dados retornados pelo model.

View (ou visualização)
É na view que o seu sistema interage com o usuário. Tudo que ele ver (HTML / XML / RSS / CSV) deve ser gerado e exibido através dessa camada. A view, por sua vez, tem como responsabilidade:
Manipular os dados para - e apenas para - exibição;
Exibir os dados.

### [Projeto MVC](https://github.com/agenciasys/as-capacita-phalcon-mvc#as-capacita-phalcon-mvc).
