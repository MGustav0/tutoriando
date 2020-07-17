# Projeto NodeJS com TypeScript

Assim está configurada a estrutura lógica, de diretórios e arquivos de um projeto back-end NodeJS com TypeScript. (2020)

Será utilizado o Data Mapper Pattern e focado nos princípios do SOLID e DDD, separando melhor as responsabilidades da aplicação entre os arquivos de rotas, services e repositories.

## Estrutura de Pastas e Arquivos

### Raíz

_src/_ - Pasta que contém todos os arquivos da aplicação.

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

Dentro da pasta `/src` teremos estas pastas `infra, entities, typeorm, repositories, http, migrations, modules, implementations, dtos, fakes, shared`.

#### Pastas

* _@types/_ - Contém arquivos de substituição de tipos das bibliotecas do NodeJS.

* _config/_ - Centraliza as configurações de autenticação e upload de arquivos.

* _modules_ - Conterá setores independentes da aplicação.

* _shared_ - Conterá as pastas e arquivos compartilhados pela aplicação.

### Pasta Modules

Dentro desta pasta os setores da aplicação serão definidos pelas regras de negócio da aplicação, por exemplo, conterá uma pasta de usuários caso a aplicação tenha usuários, e dentro dessas pastas conterão as seguintes pastas:

> Pasta infra

* _infra_ - Contém os arquivos e pastas responsáveis por um pacote ou biblioteca específica para realizar alguma tarefa, não fazendo parte das regras de negócio, mas suportando-as. As alterações de tecnologia podem ser realizadas sem comprometer as regras de negócio da aplicação. Contém as seguintes pastas: `http e database`.

  * _orm/_ - Contém criação genérica da conexão com o ORM (qualquer um) e a pasta das migrations criadas pelo ORM.

    * _entities/_ - Contém os modelos de dados, as informações abstraídas e representadas, essas informações podem ser salvas no banco de dados, também representações das relações entre entidades.

* _repositories/_ - Contém os arquivos que são uma ponte entre a aplicação e a fonte de dados. Abstração das lógicas comuns de operações no banco (CRUD).

* _services/_ - Contém os arquivos de regras de negócio da aplicação.

### Pasta Shared

Conterá as seguintes pastas compartilhadas pela aplicação: `infra e http`.

> Pasta infra

* _infra_ - Contém os arquivos e pastas responsáveis por um pacote ou biblioteca específica para realizar alguma tarefa, não fazendo parte das regras de negócio, mas suportando-as. As alterações de tecnologia podem ser realizadas sem comprometer as regras de negócio da aplicação. Contém as seguintes pastas: `http e orm`.

  * _orm/_ - Contém criação genérica da conexão com o ORM (qualquer um) e a pasta das migrations criadas pelo ORM.

> Pasta http

* _http_ - Contém todos os arquivos relacionados à camada de comunicação HTTP da aplicação estará aqui, como middleware de rotas HTTP, as rotas e o arquivo de servidor.

  * _middlewares_ - Contém os middleware da aplicação.

  * _errors/_ - Centraliza os erros conhecidos da aplicação em uma única pasta.

  * _routes/_ - Rotas da aplicação, contém middleware. Recebe uma requisição, repassa os dados da requisição a outro arquivo e devolve uma resposta.

  * _server.ts_ - Arquivo que contém a classe que iniciará a Aplicação, contém o construtor que iniciará o servidor, as rotas, os middleware, arquivos de erros e conexão com o banco de dados.

Obs.: As pastas **sempre** podem variar de acordo com a regra de negócio da aplicação e o time de desenvolvimento. São apenas sugestões para melhorar a organização do código.
