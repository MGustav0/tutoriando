# ORM

Para utilizar o ORM TypeORM, basta inserir as linhas de código abaixo, ela criará a conexão do TypeORM com o banco de dados.

O código a seguir é específico do TypeORM. Cada ORM será criado de um jeito específico, consulte a documentação sempre, pois podem haver atualizações. Para cada ORM utilizado aconselha-se à utilizar uma pasta específica.

Cria-se na pasta do módulo: `src/shared/infra/typeorm/index.ts`.

```js
import { createConnections } from 'typeorm';

createConnections();

```

Para configurar a conexão com o banco de dados o TypeORM utiliza um arquivo JSON, o exemplo a seguir é para o banco PostgreSQL e MongoDB.

Cria-se o arquivo: `ormconfig.json`.

```json
[
  {
    "name": "default",
    "type": "postgres",
    "host": "localhost",
    "port": 5432,
    "username": "postgres",
    "password": "SuaSenha",
    "database": "nomeDoBanco",
    "entities": [
      "./src/modules/**/infra/typeorm/entities/*.ts"
    ],
    "migrations": [
      "./src/shared/infra/typeorm/migrations/*.ts"
    ],
    "cli": {
      "migrationsDir": "./src/shared/infra/typeorm/migrations"
    }
  },
  {
    "name": "mongo",
    "type": "mongodb",
    "host": "localhost",
    "port": 27017,
    "database": "nomeDoBanco",
    "useUnifiedTopology": true,
    "entities": [
      "./src/modules/**/infra/typeorm/schemas/*.ts"
    ]
  }
]

```
