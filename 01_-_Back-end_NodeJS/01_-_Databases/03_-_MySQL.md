# Docker

Instalação e configuração de containeres para banco de dados.

## MySQL

Para criar uma imagem do **MySQL**, basta colocar o seguinte comando no terminal:

* ```docker run --name mysql01 -e MYSQL_ROOT_PASSWORD=docker -d -p 3306:3306 mysql```
* Verificar se a imagem está rodando: ```docker ps```
* Verificar os logs da imagem (nome_da_imagem = database): ```docker logs nome_da_imagem```
* Acesso pelo terminal: ```docker exec -it nome_do_container bash```

## phpMyAdmin

Para criar uma imagem do **phpMyAdmin4**, basta colocar o seguinte comando no terminal:

* ```docker run --name phpmyadmin01 -d --link mysql01:db -p 8080:80 phpmyadmin/phpmyadmin```
* Coloque a porta que estiver livre, no caso a **8080**.
* O terminal ficará ocupado até o final da operação/uso.
* Acesse pelo browser o [localhost](http://localhost:8080/ "localhost")
* Nas configurações iniciais o **_host name/address_** deverá ser: ```host.docker.internal```

**Obs.:** Caso não consiga acessar o phpMyAdmin por causa desses erros:

* ```#2054 - The server requested authentication method unknown to the client```
* ```mysqli_real_connect(): The server requested authentication method unknown to the client [caching_sha2_password]```
* ```mysqli_real_connect(): (HY000/2054): The server requested authentication method unknown to the client```

Acesse a imagem utilizando o terminal e o comando de acesso pelo docker e execute esta sequência de comandos:

1. ```mysql -u root -p```
2. ```ALTER USER 'root' IDENTIFIED WITH mysql_native_password BY 'docker';```
