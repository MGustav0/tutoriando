# Titulo ou Arte do Projeto

![Badge](https://img.shields.io/badge/types-Flow%20%7C%20TypeScript-blue)
![Badge](https://img.shields.io/badge/Bootcamp%20Rocketseat-React%20Native-blueviolet)
![Badge](https://img.shields.io/badge/node-%3E%3D%2012.18.2-brightgreen)

> Status do Projeto: (✔️ concluído ou 🚧 em desenvolvimento)

## Tópicos

🔹 [Descrição do projeto](#🚀-sobre-o-desafio)

🔹 [Template da aplicação](#📓-template-da-aplicação)

🔹 [Funcionalidades](#ℹ️-funcionalidades)

🔹 [Pré-requisitos](#✨-pré-requisitos)

🔹 [Como configurar banco de dados](#💾-iniciar/configurar-banco-de-dados)

🔹 [Como rodar a aplicação](#▶️-como-rodar-a-aplicação)

🔹 [Como rodar os testes](#🏗-como-rodar-os-testes)

🔹 [Insomnia](#😴-insomnia)

🔹 [Layout da Aplicação](#💻-layout-da-aplicação)

🔹 [Resolvendo Problemas](#❗️-resolvendo-problemas)

🔹 [Tarefas em aberto](#📝-tarefas-em-aberto)

## 🚀 Sobre o desafio

<p align="justify">
  Nesse desafio, irei desenvolver a aplicação a GoRestaurant, na versão mobile para o cliente.
  <br>
  Essa será uma aplicação que irá se conectar a uma Fake API, e exibir e filtrar os pratos de comida da API e permitir a criação de novos pedidos.
</p>

## 📓 Template da aplicação

O template original utilizado é o que a Rocketseat disponibilizou na seguinte url: **[Acessar Template](https://github.com/Rocketseat/gostack-template-reactjs-crud)**

**Dica**: Caso não saiba utilizar repositórios do Github como template, temos um guia no **[FAQ](https://github.com/Rocketseat/bootcamp-gostack-desafios/tree/master/faq-desafios).**

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

Agora navegue até a pasta criada e abra no Visual Studio Code, lembre-se de executar o comando `yarn` no seu terminal para instalar todas as dependências.

Execute `yarn start` para inicializar a aplicação.

Pronto! Agora basta acessar a aplicação à partir do link: http://localhost:3000/

### Passos para mobile

A fazer.

## 🏗 Como rodar os testes

```bash
yarn test
```

## 😴 Insomnia

Para fazer o download do [insomnia](https://insomnia.rest/download/), para utilizar o mesmo workspace utilizado no projeto clique [aqui]().

## 💻 Layout da Aplicação

> Link do deploy da aplicação. Exemplo com netlify: https://certificates-for-everyone-womakerscode.netlify.app/

Se ainda não houver deploy, insira capturas de tela da aplicação ou gifs.

### Título da imagem

<img src="" max-width="700" max-heigth="600" />

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

Desafio proposto com 💜 by Rocketseat 👋

The [MIT License](https://opensource.org/licenses/MIT) - Use freely, I am not responsible for the actions of third parties.

©️ Copyright? 2020 - Proffy - Intellectual property does not exist! Copying Is Not Theft.
