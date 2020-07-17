# Docker

Instalação e configuração de containeres para banco de dados.

## PostgreSQL

Para criar uma imagem do **PostgreSQL**, basta colocar o seguinte comando no terminal:

* Se quiser que o container inicie com o docker: ```-dit --restart always```, se não basta removê-lo.
* ```docker run --name postgresBD -e POSTGRES_PASSWORD=docker -d -p 5432:5432```
* Dados do Banco:
  * Nome da Imagem Docker: postgresBD
  * Usuário: postgres
  * Senha: docker
* Verificar se a imagem está rodando: ```docker ps```
* Verificar os logs da imagem (nome_da_imagem = database): ```docker logs nome_da_imagem```
* Acesso pelo terminal: ```docker exec -it nome_do_container bash```

## PGAdmin

Para criar uma imagem do **PGAdmin4**, basta colocar o comando no terminal:

* ```docker run -p 5555:80 --name pgadmin01 -e 'PGADMIN_DEFAULT_EMAIL=postgres' -e 'PGADMIN_DEFAULT_PASSWORD=docker' dpage/pgadmin4```
* Coloque a porta que estiver livre, no caso a **5555**.
* O terminal ficará ocupado até o final da operação/uso.
* Acesse pelo browser o [localhost](http://localhost:5555/ "localhost")
* Nas configurações iniciais o **_host name/address_** deverá ser: ```host.docker.internal```
