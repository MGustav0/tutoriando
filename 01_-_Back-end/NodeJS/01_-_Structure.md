# Projeto NodeJS com TypeScript

Assim está configurada a estrutura lógica, de diretórios e arquivos de um projeto back-end NodeJS com TypeScript que utilizarei. (2020)

Será utilizado o Data Mapper Pattern e focado nos princípios do SOLID e DDD, separando melhor as responsabilidades da aplicação entre os arquivos de rotas, services e repositories.

## Estrutura de Pastas e Arquivos

### Raíz

`src/` - Pasta que contém todos os arquivos da aplicação.

_Arquivos de configuração_ - Conterá outros arquivos de configuração:

* VSCode: .editorconfig
* EsLint: .eslintrc.json e .eslintignore
* Git: .gitignore
* TypeORM: ormconfig.json
* Aplicação: package.json
* Prettier: prettier.config.js
* TypeScript: tsconfig.json
* Yarn: yarn.lock

### Pasta SRC

#### Pastas

* `@types/` - Contém arquivos de substituição de tipos das bibliotecas do NodeJS.

* `config/` - Centraliza as configurações de autenticação e upload de arquivos.

* `modules/` - Conterá setores independentes da aplicação.

* `shared/` - Conterá as pastas e arquivos compartilhados pela aplicação.

### Pasta Modules

Dentro desta pasta os setores da aplicação serão definidos pelas regras de negócio da aplicação, por exemplo, conterá uma pasta de usuários caso a aplicação tenha usuários, e *dentro dessas pastas* conterão as seguintes pastas:

* `dtos/` - Aqui estão os aquivos compostos tipados para CRUD e que podem se repetir na aplicação, usado para transferir dados entre subsistemas. Pode conter interface para criação de um objeto/módulo, repassa várias informações do objeto para o *repositório do domínio*.

* `infra/` - Contém os arquivos e pastas responsáveis por um pacote ou biblioteca específica para realizar alguma tarefa, não fazendo parte das regras de negócio, mas suportando-as e isolando-as da camada de domínio. As alterações de tecnologia podem ser realizadas sem comprometer as regras de negócio da aplicação. Contém as seguintes pastas:

  * `http/` - Contém todos os arquivos relacionados à camada de comunicação HTTP da aplicação estará aqui, como middleware de rotas HTTP, as rotas e o arquivo de servidor.

    * `controllers/` - Os Controllers são usados para executar as regras de negócio da aplicação, configura o que cada rota faz, repassa informações para o service e recebe a informação. Cada controller é responsável por uma funcionalidade ou regra de negócio.

    * `routes/` - Rotas da aplicação recebem uma requisição, repassam os dados da requisição a outro arquivo (controller) recebem os dados processados e devolvem uma resposta.
  
  * `middlewares/` - Contém os middleware da aplicação.

  * `orm/` - Contém as entidades baseadas no ORM em uso.

    * `entities/` - Contém os modelos de dados, as informações abstraídas e representadas, essas informações podem ser salvas no banco de dados, também representações das relações entre entidades.

  * `providers/` - Proveem alguma funcionalidade específica para a aplicação, podem ser regras de negócio, mas para respeitar o _Single Responsibility Principle_ e o _Dependency Inversion Principle_ não podem ser criados nos `services`, para não terem mais de uma responsabilidade.

    * `PastaComNomeDoProvedor/` - Funcionalidade específica.

      * `fakes` - Contém os repositórios para os testes.

      * `implementations` - Implementação do provedor.

      * `models` - Contém a interface, os métodos que um provedor precisa ter para se comunicar com a aplicação.

  * `repositories/` - Contém os arquivos que são uma ponte entre a aplicação e a fonte de dados. Neles estão contidos os métodos de CRUD, segundo o ORM. Ao trocar de ORM, basta alterar esses arquivos para o padrão do ORM escolhido.

* `repositories/` - Contém os arquivos que são uma interface, uma abstração das regras de negócio, são contratos a serem implementados nos services, eles ditam como o repositório do ORM deve se comportar.

* `services/` - Contém os arquivos que isolam regras de negócio da aplicação.

### Pasta Shared

Conterá as seguintes pastas compartilhadas pela aplicação: `infra e http`.

* `container` - Controle de injeção das dependências da aplicação.
  
  * `providers/` - Proveem alguma funcionalidade específica para a aplicação, neste caso compartilhadas, podem ser regras de negócio, mas para respeitar o _Single Responsibility Principle_ e o _Dependency Inversion Principle_ não podem ser criados nos `services`, para não terem mais de uma responsabilidade.

    * `PastaComNomeDoProvedor/` - Funcionalidade específica.

      * `fakes` - Contém os repositórios para os testes.

      * `implementations` - Implementação do provedor.

      * `models` - Contém a interface, os métodos que um provedor precisa ter para se comunicar com a aplicação.

* `errors/` - Centraliza os erros conhecidos da aplicação em uma única pasta.

* `infra/` - Contém os arquivos e pastas responsáveis por um pacote ou biblioteca específica para realizar alguma tarefa, não fazendo parte das regras de negócio, mas suportando-as. As alterações de tecnologia podem ser realizadas sem comprometer as regras de negócio da aplicação. Contém as seguintes pastas e arquivos:

  * `http` - Contém todos os arquivos relacionados à camada de comunicação HTTP da aplicação estará aqui, como middleware de rotas HTTP, as rotas e o arquivo de servidor.

    * `routes/` - Rotas da aplicação, contém middleware. Recebe uma requisição, repassa os dados da requisição a outro arquivo e devolve uma resposta.
  
  * `middlewares/` - Contém os middleware da aplicação.
  
  * `orm/` - Contém criação genérica da conexão com o ORM (qualquer um) e a pasta das migrations criadas pelo ORM.

  * `server.ts` - Arquivo que contém a classe que iniciará a Aplicação, contém o construtor que iniciará o servidor, as rotas, os middleware, arquivos de erros e conexão com o banco de dados.

Obs.: As pastas *sempre* podem variar de acordo com a regra de negócio da aplicação e o time de desenvolvimento. São apenas sugestões para melhorar a organização do código.
