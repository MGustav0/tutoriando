# Docker

Instalação e configuração de containeres para banco de dados.

## MongoDB

### linha de comando

Para criar uma imagem do **MongoDB**, basta colocar o seguinte comando no terminal:

* Se quiser que o container inicie com o docker: ```-dit --restart always```, se não basta removê-lo.
* Criar sem senha (recomendável para desenvolvimento): ```docker run --name mongoBarber -p 27017:27017 -d -t mongo```
* Criar com senha: ```docker run --name nome_de_producao -p 27017:27017 -e MONGODB_PASS="mypass" -t mongo```
* Verificar se a imagem está rodando: ```docker ps```
* Verificar os logs da imagem (nome_da_imagem = database): ```docker logs nome_da_imagem```
* Usuário:
* Senha:
* Acesso pelo terminal: ```docker exec -it nome_do_container bash```

### docker-compose

```yml
mongoDb:
    image: mongo
    container_name: rocketSocketMongo
    ports:
      - "27017:27017"
```

Dica: Se utilizar a biblioteca [mongoose](https://mongoosejs.com/) junto com o **docker-compose**, no lugar da URL, passe o nome que você deu ao serviço, nesse caso:

Ao invés de:

```js
mongoose.connect('mongodb://localhost:27017/db_name');
```

Coloque assim:

````js
mongoose.connect('mongodb://mongo:27017/db_name');
````
