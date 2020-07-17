# Guia de Inicialização

Este guia visa mostrar o passo a passo para inicialização de uma aplicação NodeJS com TypeScript, com as configurações iniciais para um projeto.

## Requisitos

1. Ter Yarn v1 instalado;
2. Ter o NodeJS instalado.

## Criando o Projeto

1. Criar um pasta com o para o projeto.

2. Criar o projeto, digitar no terminal dentro da pasta do projeto `yarn init` e configurar as opções desejadas.

## Dependênias

### Produção

```zsh
yarn add express
```

### Desenvolvimento

```zsh
yarn add typescript @types/express ts-node-dev eslint-import-resolver-typescript -D
```

Gerar o arquivo de configuração do TypeScript: `yarn tsc --init`;

Acessar o arquivo `/tsconfig.json` que fora gerado, descomentar e editar as linhas `"rootDir": "./src"` e `"outDir": "./dist"`.

## TypeScript

Criar a pasta `/src` e o arquivo `src/server.js`, pode ter outros nomes, mas como geralmente o node é o servidor da aplicação, pode-se utilizar esse nome.

Criar a pasta `/dist`, aqui ficará o build da aplicação. Para converter o arquivo para o de distribuição no formato JavaScript: `yarn tsc`.

Nos scripts do `package.json`, adiciona-se a linha `"build": "tsc"`, assim pode realizar o build apenas digitando `build` no terminal.

Para evitar a construção do bild para JavaScript toda vez que executar a aplicação, além do nodemon, pode ser utilizada a dependência ts-node-dev para desenvolvimento e configurar nos scripts do `package.json` adicionando a linha `"dev:server": "ts-node-server --transpileOnly --ignore-watch node_modules src/server.ts"`.

O **dev** é um agregador que podemos criar antes do **:** e nomear o servidor e qualquer outra feature, como as filas de e-mails, assim pode-se chamar apenas por `yarn dev` no terminal para que todas as features sob o **dev** sejam chamadas.

O `--transpileOnly` evita a checagem de código (tipos, erros, etc.) essa parte fica a cargo do próprio VS Code.

O `--ignore-watch node_modules` não irá compilar a pasta _Node Modules_, pois como normalmente ela não será alterada pelo desenvolvedor, não faz sentido monitorar alteraÇão de código nesta pasta, o que ajuda na performance.

## Express

Configurar o servidor é uma das coisas primárias à se fazer, pois esse arquivo não será alterado constantemente.

Importar a biblioteca ExpressJS no arquivo `server.js`.

Despois de criado, o arquivo servirá para ser chamado onde for necessário ser utilizado.

**Obs.: Sempre que o EsLint apontar erro após a instalação de uma biblioteca, faz-se necessário instalar o padrão de tipos para o TypeScript: `yarn add @types/express -D`.**

Adicionar o `app.use(express.json())` para que a aplicação possa entender o formato _.json_ nas requisições.

### server.ts

```typescript
import app from './app';

app.listen(3333, () => {
  console.log('🚀 Server started on port 3333!');
});
```

## Rotas

Uma boa prática é criá-la separadamente, em uma pasta de rotas `/src/routes`, o arquivo principal de rotas pode ser o `index.ts` dentro da pasta. As rotas devem ser importadas neste arquivo.

```typescript
import { Router } from 'express';

import minhaRotaRouter from './minhaRota.routes';

const routes = Router();

routes.use('/minharota', minhaRotaRouter);

export default routes;
```

O arquivo de rota importado deve ficar na mesma pasta e receberá os comandos e outros arquivos via importação.

### minhaRota.routes

```typescript
import { Router } from 'express';

import meuRepositorioRepository from '../repositories/meuRepositorioRepository';
import meuServiceService from '../services/meuServiceService';

const rotaRouter = Router();

rotaRouter.get('/', async (request, response) => {
  // TODO
});

rotaRouter.post('/', async (request, response) => {
  // TODO
});

rotaRouter.delete('/:id', async (request, response) => {
  // TODO
});

export default rotaRouter;
```

## Services

## Models

## Repositories

## Database

## Erros
