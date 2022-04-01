# PostgreSQL

## Docker

Normalmente a instalação dos bancos de dados é feita através de um pacote de terceiros, como o [Docker](https://hub.docker.com/_/postgres), que é um container que pode ser instalado no computador e rodar separado do sistema operacional.

### Dockerfile

Podemos instalar o PostgreSQL juntamente com outros e rodar com apenas um comando.

Configuramos o docker com uma Dockerfile, configurando o node, instalando o typescript e rodando o yarn, configurando para development e production:

```Dockerfile
FROM node:16.14.2

WORKDIR /usr/src/app

RUN npm i -g typescript

COPY . .

RUN yarn install --only=development && \
  yarn build && \
  yarn install --production=true # reduce image size

CMD ["node", "dist/src/main"]
```

Instale também o [docker-compose](https://docs.docker.com/compose/install/). Ao dar o comando `docker-compose up` ele irá carregar todos os contêineres listados nesse arquivo:

```yaml
version: "3.9"

services:

  # main:
  #   container_name: main
  #   build:
  #     context: .
  #     target: development
  #   volumes:
  #     - .:/usr/src/app — /usr/src/app/node_modules
  #   ports:
  #     - 3000:3000
  #   command: yarn start:dev
  #   env_file:
  #     - .env
  #   depends_on:
  #     - postgres

  postgres:
    image: postgres:14.2
    container_name: postgres
    ports:
      - "5432:5432"
    volumes:
      - ./var/postgresql:/var/lib/postgresql/data:rw
      - ./cli:/cli
    env_file:
      - .env

```

Use `docker-compose up -d` para modo detached, para que o container não seja fechado quando o terminal fechar.

### Docker CMD

Para criar uma imagem do **PostgreSQL**, basta colocar o seguinte comando no terminal:

* Se quiser que o container inicie com o docker: ```-dit --restart always```, se não basta removê-lo.
* ```docker run --name postgresBD -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres```
* Dados do Banco:
  * Nome da Imagem Docker: postgresBD
  * Usuário: postgres
  * Senha: docker
* Verificar se a imagem está rodando: ```docker ps```
* Verificar os logs da imagem (nome_da_imagem = database): ```docker logs nome_da_imagem```
* Acesso pelo terminal: ```docker exec -it nome_do_container bash```

### PGAdmin CMD

Para criar uma imagem do **PGAdmin4**, que é uma interface web para o postgres, basta colocar o comando no terminal:

* ```docker run -p 5555:80 --name pgadmin01 -e 'PGADMIN_DEFAULT_EMAIL=postgres' -e 'PGADMIN_DEFAULT_PASSWORD=docker' dpage/pgadmin4```
* Coloque a porta que estiver livre, no caso a **5555**.
* O terminal ficará ocupado até o final da operação/uso.
* Acesse pelo browser o [localhost](http://localhost:5555/ "localhost")
* Nas configurações iniciais o **_host name/address_** deverá ser: ```host.docker.internal```
