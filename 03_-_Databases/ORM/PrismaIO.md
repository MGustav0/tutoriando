# PrismaIO

[Prisma](https://www.prisma.io/) é um projeto OpenSource e que segundo o próprio time pode ser considerado uma especie de ORM que substitui os tradicionais. O Prisma é uma camada de acesso a base de dados, ele faz a abstração do acesso a base de dados e roda em um container Docker, que através de uma CLI fornecida por eles é realizado o acesso ao serviço.

Além da abstração ele também possui um gerenciador de migrações que controla todas as alterações na estrutura de dados do banco. O código gerado é chamado de prisma-client que é uma api muito flexível que possibilita seu uso em diversos casos de uso, como REST APIs, CLIs, aplicações baseadas em microservices e GraphQL APIs, que é compatível com o ecossistema Apollo, tem suporte padrão para subscriptions GraphQL e paginação estilo Relay, oferece segurança ponta-a-ponta e vem com um dataloader integrado para resolver o [problema N+1](https://medium.com/slite/avoiding-n-1-requests-in-graphql-including-within-subscriptions-f9d7867a257d).

## Como usar

O presente tutorial irá mostrar como usar o Prisma no VSCode apenas.

### Instalando extensão no VSCode

Baixe as seguintes extensões [Prisma](https://marketplace.visualstudio.com/items?itemName=Prisma.prisma) e [Prisma - Insider](https://marketplace.visualstudio.com/items?itemName=Prisma.prisma-insider) que auxiliarão na formatação de código e outras coisas.

### Configurando Prisma no projeto

Instale a biblioteca do prisma no projeto: `yarn add prisma` e depois execute: `yarn prisma init` para ele construir as configurações.

Dentro do `.env` gerado, altere as configurações para o seu banco de dados, como neste exemplo do postgres:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/your-database-name?schema=public"
```

### Prisma Studio

É uma GUI para visualizar e editar dados em seu banco de dados.

Pode ser baixada no site do [Prisma](https://www.prisma.io/studio) ou instalado no projeto e ser executado a partir dali: `yarn prisma studio`. Alterações nas migrations fazem com que o Prisma Studio instalado via biblioteca deixe de funcionar, portanto terá que reiniciar o Prisma Studio. Por padrão ele abre seu navegador default na porta 5555.

### Prisma Client

Por padrão os models são inseridos no caminho `prisma/schema.prisma` e as migrations no caminho `prisma/migrations`.

[Neste projeto](https://github.com/MGustav0/prismaIOTest) há vários exemplos de uso do Prisma.
