# Guia de Inicialização

Este guia visa mostrar o passo a passo para inicialização de uma aplicação NodeJS com TypeScript, com as configurações iniciais para um projeto.

## Requisitos

1. Ter Yarn v1 instalado;
2. Ter o NodeJS instalado.

## Criando o Projeto

1. Criar um pasta com o para o projeto.

2. Criar o projeto, digitar no terminal dentro da pasta do projeto `yarn init` e configurar as opções desejadas.

## Dependências

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

Criar a pasta `/src` e o arquivo `src/shared/infra/http/server.ts`, pode ter outros nomes, mas como geralmente o node é o servidor da aplicação, pode-se utilizar esse nome e caminho.

A pasta `/dist` será criada automaticamente a partir do comando no `package.json`, nela ficará a build da aplicação. Para converter o arquivo para o de distribuição no formato JavaScript use: `yarn tsc`.

Digite `yarn build` no terminal para fazer o build da aplicação.

Digite `yarn dev:server` no terminal para fazer inicializar o servidor como desenvolvedor.

### Caminhos relativos

Como o arquivo `/tsconfig.json` foi configurado com o _path_:

```json
"paths": {
  "@modules/*": ["modules/*"],
  "@config/*": ["config/*"],
  "@shared/*": ["shared/*"]
},
```

Cada importação começará com `import nomedomodulo from '@nomedomodulo'`, caso queira adicionar mais caminhos-base, basta adicionar de forma semelhante como demonstrado acima.

## Express

Configurar o servidor é uma das coisas primárias à se fazer, pois esse arquivo não será alterado constantemente.

**Obs.: Sempre que o EsLint apontar erro após a instalação de uma biblioteca, faz-se necessário instalar o padrão de tipos para o TypeScript: `yarn add @types/express -D`.**

## Injeção de dependências

O tsyringe nos permitirá automatizar a injeção de dependências. Para aplicar no projeto adicione `yarn add tsyringe`.

Com isto poderemos injetar as dependências sem a necessidade de passar manualmente o repositório no constructor do service, fazendo desta forma:

```js
@inserirDecorator
```

Mais sobre injeção de dependências no capítulo **NOME DO CAPÍTULO**

## Segurança

CORS (Cross-Origin Resource Sharing), é um middleware que permite que um site acesse recursos de outro site mesmo estando em domínios diferentes. Um site só pode ser chamado por outro site se os 2 sites estiverem sob o mesmo domínio, o que limita a chamada de APIs REST por aplicações JS, por exemplo, hospedadas em servidores diferentes.

Evita que outros front-ends façam requisições à Api.

Instale o cors `yarn add cors`

No _app.js_, adicione o código:

```javascript
import cors from 'cors';

//(...)

middlewares() {
    this.server.use(cors());
  }
```

Deixar ele vazio, permite acesso irrestrito. Para colocar os endereços autorizados:

```javascript
middlewares() {
    this.server.use(cors({
      'http://localhost:3000'
    }));
  }
```

## Servidor.ts

Em `src/shared/infra/http/server.ts` colar o seguinte código:

```typescript
import app from './app';

app.listen(3333, () => {
  console.log('🚀 Server started on port 3333!');
});
```

Assim quando der o comando `yarn dev:server` o servidor será iniciado na porta 3333.
