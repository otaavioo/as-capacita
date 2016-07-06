# API REST - Webservices

Um Webservice é um método de comunicação entre serviços web e pode ser qualquer tipo de serviço que comunica em um formato padrão (XML/SOAP ou JSON por exemplo).

Para este curso falaremos sobre as APIs REST.

As APIs REST se utilizam do protocolo HTTP, como foi definido originalmente pela [RFC 1945](https://datatracker.ietf.org/doc/rfc1945/).

Mais abaixo teremos uma tabela mostrando as relações entre um CRUD de um recurso e os métodos HTTP utilizados para cada operação.

Elas fazem uso dos métodos padrões do protocolo HTTP (métodos, content type, códigos padrões de retorno), fornecendo APIs de acesso para serviços web, vocês já devem ter ouvido falar em APIs de desenvolvimento do Twitter ou Facebook.

Também não possui estado entre as comunicações (sessão/cookies definidos) então cada comunicação é independente, passando toda a informação necessária no corpo e no cabeçalho.

É atualmente muito utilizada por sua facilidade de implementação e facilidade de uso. Um desenvolvedor não precisa saber como é a arquitetura ou armazenamento dos dados de um serviço específico. Ele sabe que pedindo a informação X ele receberá ela em um formato padrão, facilitando assim a manipulação dos dados. Também facilita a escalabilidade e portabilidade de um serviço.

Por isto é tão utilizada na atualidade, podendo assim ter um ponto central para desenvolvimento de aplicações ou mashups. Principalmente para facilitar o desenvolvimento de clients diferenciados e específicos para cada plataforma (Web, Mobile, TV). O servidor não precisa mudar, o que muda é o client, se tornando assim uma camada intermediária entre os dados salvos e a aplicação em sí (que é quem mantém realmente o estado de uma conexão/sessão).

Cada um define como quiser sua API, ao contrário de SOAP onde tudo é definido oficialmente. Apesar de termos alguns conceitos e boas práticas.


Cada "entidade"/tabela é um recurso a ser utilizado. Abaixo alguns exemplos do que seria um recurso e o que é feito atualmente em uma aplicação web.

    GET  https://app.meuservico.com.br/user/1234
    GET  https://app.meuservico.com.br/listAllUsers
    GET https://app.meuservico.com.br/user/delete/1234
    POST https://app.meuservico.com.br/newUser
    POST https://app.meuservico.com.br/updateUser.php?id=1234

Ao invés disto tudo utilizaremos apenas um recurso chamado "users" e cada método HTTP será utilizado para um contexto específico.

| Método/Verbo HTTP  | CRUD  |  Coleção de Itens (recurso /users) | Item específico (recurso /users/{id})    |
| -------------- |:----------------:|:----------------------:|:-------------------------:|
| POST  | Create  |  201 (Created), Header contém um Location com o link para o recurso criado. | 404 (Not Found) |
| GET  | Read  |  200 (OK), lista todos os usuários (use paginação, ordenação ou filtros para listas grandes) | 200, 404 se não encontrar ou tiver id inválido    |
| PUT  | Update  |  403/404 (você quer realmente deixar todos iguais ?) | 200, 404     |
| DELETE  | Delete  |  403/404 (você quer realmente remover tudo?) | 200, 404    |


Para listar todos os usuários nós chamaríamos apenas um método GET no recurso users:

    GET https://app.meuservico.com.br/users

Já para poder buscar um usuário específico utilizaríamos:

    GET https://app.meuservico.com.br/users/123

Para criar um novo usuário:

    POST https://app.meuservico.com.br/users

Para editar um usuário existente:

    PUT https://app.meuservico.com.br/users/123

Para remover um usuário específico:

    DELETE https://app.meuservico.com.br/users/123

Com estes padrões, fica muito mais prático, organizado e flexível o desenvolvimento de serviços backend.

Para definições de padrões e arquitetura de APIs REST, recomendo este pequeno e-book (em Inglês), precisa de um registro com e-mail, mas vale a pena: <https://pages.apigee.com/web-api-design-website-h-ebook-registration.html>
