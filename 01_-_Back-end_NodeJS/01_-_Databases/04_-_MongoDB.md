# Docker

Instalação e configuração de containeres para banco de dados.

## MongoDB

Para criar uma imagem do **MongoDB**, basta colocar o seguinte comando no terminal:

* Se quiser que o container inicie com o docker: ```-dit --restart always```, se não basta removê-lo.
* Criar sem senha (recomendável para desenvolvimento): ```docker run --name mongoBarber -p 27017:27017 -d -t mongo```
* Criar com senha: ```docker run --name nome_de_producao -p 27017:27017 -e MONGODB_PASS="mypass" -t mongo```
* Verificar se a imagem está rodando: ```docker ps```
* Verificar os logs da imagem (nome_da_imagem = database): ```docker logs nome_da_imagem```
* Usuário:
* Senha:
* Acesso pelo terminal: ```docker exec -it nome_do_container bash```
