# Titulo ou Arte do Projeto

![Badge](https://img.shields.io/badge/Bootcamp%20Rocketseat-ReactJS-blueviolet)
![Badge](https://img.shields.io/badge/types-Flow%20%7C%20TypeScript-blue)
![Badge](https://img.shields.io/badge/Bootcamp%20Rocketseat-React%20Native-blueviolet)
![Badge](https://img.shields.io/badge/node-%3E%3D%2012.18.2-brightgreen)
![Badge](https://img.shields.io/badge/PostgreSQL-v12.0-lightblue)
![Badge](https://img.shields.io/badge/MongoDB-4.4.0-green)
![Badge](https://img.shields.io/badge/Redis-6.0.6-red)

> Status do Projeto: (✔️ concluído ou 🚧 em desenvolvimento)

## Tópicos

🔹 [Descrição do projeto](#🔗-descrição-do-projeto)

🔹 [Funcionalidades](#ℹ️-funcionalidades)

🔹 [Pré-requisitos](#✨-pré-requisitos)

🔹 [Como configurar a aplicação](#💾-iniciar/configurar-banco-de-dados)

🔹 [Como rodar a aplicação](#▶️-como-rodar-a-aplicação)

🔹 [Como rodar os testes](#🏗-como-rodar-os-testes)

🔹 [Insomnia](#😴-insomnia)

🔹 [Layout da Aplicação](#💻-layout-da-aplicação)

🔹 [Resolvendo Problemas](#❗️-resolvendo-problemas)

🔹 [Tarefas em aberto](#📝-tarefas-em-aberto)

🔹 [Tarefas em aberto](#🐙-desenvolvedores)

## 🔗 Descrição do projeto

<p align="justify">
  Descrição breve do projeto compondo um paragrafo ou dois.
</p>

## ℹ️ Funcionalidades

✔️ Funcionalidade 1  

✔️ Funcionalidade 2  

❌ Funcionalidade 3  

❌ Funcionalidade 4

## ✨ Pré-requisitos

⚠️ [Node](https://nodejs.org/en/download/)

⚠️ [Yarn](https://yarnpkg.com/getting-started/install)

⚠️ [Docker](https://www.docker.com/products/docker-desktop)

⚠️ [PostgreSQL Docker](https://hub.docker.com/_/postgres)

⚠️ [MongoDB Docker](https://hub.docker.com/_/mongo)

⚠️ [Redis Docker](https://hub.docker.com/_/redis)

❗️ Você precisará seguir os passos a seguir para poder rodar a aplicação na sua máquina.

## 💾 Iniciar/Configurar banco de dados

Ter Docker e as imagens PostgreSQL, MongoDB e Redis instalados.

### Instalar PostgreSQL via Docker

* `docker run --name ecommerceChallengePostgres -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres`
* Verificar se a imagem está rodando: `docker ps`
* Usuário: postgres
* Senha: docker
* Acesso pelo terminal: `docker exec -it nome_do_container bash`

### Criar Banco de Dados PostgreSQL

1. Instale o DBeaver, ou outro gerenciador de Banco de Dados, ou faça por linha de comando.
2. Acesse com o usuário e senha supracitados.
3. Crie um Banco de Dados com o nome __gostack_desafio09__.
4. Crie um Banco de Dados com o nome __gostack_desafio09_tests__.

### Instalar MongoDB via Docker

* `docker run --name ecommerceChallengeMongo -p 27017:27017 -d -t mongo`
* Verificar se a imagem está rodando: `docker ps`
* Usuário: postgres
* Senha: docker
* Acesso pelo terminal: `docker exec -it nome_do_container bash`

### Instalar Redis via Docker

* `docker run --name ecommerceChallengeRedis -p 6379:6379 -d -t redis:alpine`
* Verificar se a imagem está rodando: `docker ps

## ▶️ Como rodar a aplicação

Agora navegue até a pasta criada e abra no Visual Studio Code, lembre-se de executar o comando `yarn` dentro da pasta no seu terminal para instalar todas as dependências. Após a instalação digite: `yarn dev:server`.

Pronto! Agora basta acessar a aplicação à partir do link: http://localhost:3333/

## 🏗 Como rodar os testes

```bash
yarn test
```

## 😴 Insomnia

Para fazer o download do [insomnia](https://insomnia.rest/download/), para utilizar o mesmo workspace utilizado no projeto clique [aqui]().

## 💻 Layout da Aplicação

> Link do deploy da aplicação. Exemplo com netlify: https://certificates-for-everyone-womakerscode.netlify.app/

Web

<img src="" width="640" heigth="360" />

Mobile

<img src="" width="270" heigth="480" />

## ❗️ Resolvendo Problemas

Caso encontre algum problema, bug ou erro me conte [aqui]()!

## 📝 Tarefas em aberto

🖊 Tarefa 1

🖊 Tarefa 2

🖊 Tarefa 3

## 🐙 Desenvolvedores

| [<img src="https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4>][(https://github.com/MGustav0](https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4))" width=115><br><sub>Gustavo Moreira</sub>](https://github.com/MGustav0) | [<img src="https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4>][(https://github.com/MGustav0](https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4))" width=115><br><sub>Gustavo Moreira</sub>](https://github.com/MGustav0) |  [<img src="https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4>][(https://github.com/MGustav0](https://avatars1.githubusercontent.com/u/18315899?s=460&u=54d9c6ea66f2b27120bf39dabe1d36ff22a92b9d&v=4))" width=115><br><sub>Gustavo Moreira</sub>](https://github.com/MGustav0) |
| :---: | :---: | :---:

## Licença

The [MIT License](https://opensource.org/licenses/MIT) - Use freely, I am not responsible for the actions of third parties.

©️ Copyright? 2020 - Proffy - Intellectual property does not exist! Copying Is Not Theft.
