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

_server.ts_ - Arquivo de configuração do servidor.

_app.ts_ - Contém a classe que iniciará a Aplicação, contém o construtor que iniciará o servidor, as rotas, os middlewares, arquivos de erros e conexão com o banco de dados.

_routes/_ - Rotas da aplicação, contém middlewares. Recebe uma requisição, repassa os dados da requisição a outro arquivo e devolve uma resposta.

_services/_ - Contém os arquivos de regras de negócio da aplicação.

_models/_ - Contém os modelos de dados para conexão com o banco de dados e suas relações.

_repositories/_ - Contém os arquivos que são uma ponte entre a aplicação e a fonte de dados. Abstração das lógicas comuns de operações no banco (CRUD).

_database/_ - Contém criação genérica da conexão com o banco de dados (qualquer um) e a pasta das migrations criadas pelo ORM, no caso o TypeORM (2020).

_middlewares_ - Contém os middlewares da aplicação.

_errors/_ - Centraliza os erros conhecidos da aplicação em uma única pasta.

_config/_ - Centraliza as configurações de autenticação e upload de arquivos.

_@types/_ - Contém arquivos de substituição de tipos das bibliotecas do NodeJS.
