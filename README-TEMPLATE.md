# Titulo ou Arte do Projeto

![Badge](https://img.shields.io/badge/Bootcamp%20Rocketseat-ReactJS-blueviolet)
![Badge](https://img.shields.io/badge/types-Flow%20%7C%20TypeScript-blue)
![Badge](https://img.shields.io/badge/Bootcamp%20Rocketseat-React%20Native-blueviolet)
![Badge](https://img.shields.io/badge/node-%3E%3D%2012.18.2-brightgreen)
![Badge](https://img.shields.io/badge/PostgreSQL-v12.0-lightblue)
![Badge](https://img.shields.io/badge/MongoDB-4.4.0-green)
![Badge](https://img.shields.io/badge/Redis-6.0.6-red)

> Status do Projeto: (:heavy_check_mark: concluído ou :construction: em desenvolvimento)

## Tópicos

🔹 [Descrição do projeto](#:link:-descrição-do-projeto)

🔹 [Funcionalidades](#information_source-funcionalidades)

🔹 [Pré-requisitos](#sparkles-pré-requisitos)

🔹 [Como configurar a aplicação](#floppy_disk-iniciar/configurar-banco-de-dados)

🔹 [Como rodar a aplicação](#arrow_forward-como-rodar-a-aplicação)

🔹 [Como rodar os testes](#building_construction-como-rodar-os-testes)

🔹 [Insomnia](#sleeping-insomnia)

🔹 [Layout da Aplicação](#scroll-layout-da-aplicação)

🔹 [Resolvendo Problemas](#hammer-resolvendo-problemas)

🔹 [Tarefas em aberto](#pencil-tarefas-em-aberto)

🔹 [Tarefas em aberto](#octopus-desenvolvedores)

## :link: Descrição do projeto

<p align="justify">
  Descrição breve do projeto compondo um paragrafo ou dois.
</p>

## :information_source: Funcionalidades

✔️ Funcionalidade 1  

✔️ Funcionalidade 2  

❌ Funcionalidade 3  

❌ Funcionalidade 4

## :sparkles: Pré-requisitos

⚠️ [Node](https://nodejs.org/en/download/)

⚠️ [Yarn](https://yarnpkg.com/getting-started/install)

⚠️ [Docker](https://www.docker.com/products/docker-desktop)

⚠️ [PostgreSQL Docker](https://hub.docker.com/_/postgres)

⚠️ [MongoDB Docker](https://hub.docker.com/_/mongo)

⚠️ [Redis Docker](https://hub.docker.com/_/redis)

❗️ Você precisará seguir os passos a seguir para poder rodar a aplicação na sua máquina.

## :floppy_disk: Iniciar/Configurar banco de dados

Ter Docker e as imagens PostgreSQL, MongoDB e Redis instalados.

### :elephant: Instalar PostgreSQL via Docker

* `docker run --name ecommerceChallengePostgres -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres`
* Verificar se a imagem está rodando: `docker ps`
* Usuário: postgres
* Senha: docker
* Acesso pelo terminal: `docker exec -it nome_do_container bash`

### :dolphin: Criar Banco de Dados PostgreSQL

1. Instale o DBeaver, ou outro gerenciador de Banco de Dados, ou faça por linha de comando.
2. Acesse com o usuário e senha supracitados.
3. Crie um Banco de Dados com o nome __gostack_desafio09__.
4. Crie um Banco de Dados com o nome __gostack_desafio09_tests__.

### :four_leaf_clover: Instalar MongoDB via Docker

* `docker run --name ecommerceChallengeMongo -p 27017:27017 -d -t mongo`
* Verificar se a imagem está rodando: `docker ps`
* Usuário: postgres
* Senha: docker
* Acesso pelo terminal: `docker exec -it nome_do_container bash`

### :file_folder: Instalar Redis via Docker

* `docker run --name ecommerceChallengeRedis -p 6379:6379 -d -t redis:alpine`
* Verificar se a imagem está rodando: `docker ps

## :arrow_forward: Como rodar a aplicação

Agora navegue até a pasta criada e abra no Visual Studio Code, lembre-se de executar o comando `yarn` dentro da pasta no seu terminal para instalar todas as dependências. Após a instalação digite: `yarn dev:server`.

Pronto! Agora basta acessar a aplicação à partir do link: http://localhost:3333/

## :building_construction: Como rodar os testes

```bash
yarn test
```

## :sleeping: Insomnia

Para fazer o download do [insomnia](https://insomnia.rest/download/), para utilizar o mesmo workspace utilizado no projeto clique [aqui](), baixe e importe no seu Insominia.

## :scroll: Layout da Aplicação

> Link do deploy da aplicação. Exemplo com netlify: https://certificates-for-everyone-womakerscode.netlify.app/

Web

<img src="" width="640" heigth="360" />

Mobile

<img src="" width="270" heigth="480" />

## :hammer: Resolvendo Problemas

Caso encontre algum problema, bug ou erro me conte [aqui]()!

## :pencil: Tarefas em aberto

🖊 Tarefa 1

🖊 Tarefa 2

🖊 Tarefa 3

## :octopus: Desenvolvedores

| [<img src="https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4>][(https://github.com/MGustav0](https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4))" width=115><br><sub>Gustavo Moreira</sub>](https://github.com/MGustav0) | [<img src="https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4>][(https://github.com/MGustav0](https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4))" width=115><br><sub>Gustavo Moreira</sub>](https://github.com/MGustav0) |  [<img src="https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4>][(https://github.com/MGustav0](https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4))" width=115><br><sub>Gustavo Moreira</sub>](https://github.com/MGustav0) |
| :---: | :---: | :---:

## :copyright: Licença

The [MIT License](https://opensource.org/licenses/MIT) - Use freely, I am not responsible for the actions of third parties.

©️ Copyright? 2020 - Proffy - Intellectual property does not exist! Copying Is Not Theft.
