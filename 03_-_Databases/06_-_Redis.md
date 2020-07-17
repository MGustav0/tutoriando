# Docker

Instalação e configuração de containeres para banco de dados.

## Redis - Banco performático de chave/valor

Para criar uma imagem do **Redis**, basta colocar o seguinte comando no terminal:

* Se quiser que o container inicie com o docker: ```-dit --restart always```, se não basta removê-lo.
* ```docker run --name redisBarber -p 6379:6379 -d -t redis:alpine```
* O comando ```redis:apine``` traz as features mais essenciais do linux.
* Verificar se a imagem está rodando: ```docker ps```
* Verificar os logs da imagem (nome_da_imagem = database): ```docker logs nome_da_imagem```
* Usuário:
* Senha:
* Acesso pelo terminal: ```docker exec -it nome_do_container bash```
