# Configuração Inicial

## Criar uma App

No terminal, dentro da pasta do projeto, digitar: `yarn init` e configurar o _package.json_.

Digite no terminal: `yarn add react react-dom`

Ao digitar comando `yarn create-react-app` será criado o projeto React e dentro dele duas pastas:

1. _/public_ - Contém todos os arquivos públicos, que serão acessados pelo browser, normalmente é o HTML base, o favicon e outras coisas relacionadas.
2. _/src_ - Contém todos os arquivos relacionados à funcionalidades e regras de negócio da aplicação.
3. Retire os seguintes itens da pasta `/src`:
   1. App.css
   2. App.test.jsx
   3. index.css
   4. logo.svg
   5. ServiceWorker.js
4. Retire os seguintes itens da pasta `/public`:
   1. logo192.png
   2. logo512.png
   3. favicon.ico (caso queira colocar outro favicon, sobrescreva)
   4. manifest.json (caso queira colocar outro favicon, edite)
5. Caso queira um projeto em TypeScript: `yarn create-react-app --template=typescript`
6. Editar o arquivo index.jsx/.tsx para ficar neste modelo:

```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

7. Editar o arquivo App.jsx/.tsx para ficar neste modelo:

```js
import React from 'react';

function App() {
  return (
    <>
      <h1>Hello World!</h1>
    </>
  );
}

export default App;
```

8. Editar o arquivo index.html para ficar neste modelo (com fonte Roboto):

```html
<!DOCTYPE html>
<html lang="pt-BR">
  <head>
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=n" />
    <meta name="theme-color" content="#f4ede8" />

    <title>OneRecipe</title>

    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Slab:wght@400;500;600&display=swap" rel="stylesheet">
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>
```

## Instalar dependências

### dependencies

```bash
yarn add styled-components
```

### devDependencies

## Definir os estilos globais

Criar a pasta e arquivo `src/styles/global.ts` e inserir o seguinte código:

```js
import { createGlobalStyle } from 'styled-components';

export default createGlobalStyle`
  * {
    margin: 0;
    padding: 0;
    outline: 0;
    box-sizing: border-box;
  }

  body {
    // Coloque as cores padrão de sua aplicação
    background: #312E38;
    color: #FFF;
    -webkit-font-smoothing: antialiased
  }

  body, input, button {
    font: "Roboto Slab", serif;
    font-size: 16px;
  }

  hanging-punctuation, h2, h3, h4, h5, h6, strong {
    font-weight: 500;
  }

  button {
    cursor: pointer;
  }
`;
```

Faça a importação no `src/App.tsx`:

```js
import React from 'react';
import { BrowserRouter } from 'react-router-dom';

import GLobalStyle from './styles/global';

import Routes from './routes';

const App: React.FC = () => (
  <BrowserRouter>
    <Routes />
    <GLobalStyle />
  </BrowserRouter>
);

export default App;
```

## Linters

Para instalar os linters acesse esses conteúdos em [07_-_Code_Formatters](https://github.com/MGustav0/tutoriando/tree/master/07_-_Code_Formatters):

1. [03_-_ESLint_-_ReactJS](https://github.com/MGustav0/tutoriando/blob/master/07_-_Code_Formatters/03_-_ESLint_-_ReactJS.md)
2. [01_-_Prettier](https://github.com/MGustav0/tutoriando/blob/master/07_-_Code_Formatters/01_-_Prettier.md)

Se ainda não configurou o VSCode, acesse este [conteúdo](https://github.com/MGustav0/tutoriando/blob/master/07_-_Code_Formatters/01_-_VSCode.md).

**Reinicie o VSCode**
