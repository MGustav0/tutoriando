# Pretier

É um formatador de código para atuar em conjunto com o ESLint, que faz o embelezamento do código, como quebra de linhas e outras coisas.

## Instalação

```node
yarn add prettier eslint-config-prettier eslint-plugin-prettier -D
```

## Arquivo de configuração

Criar o arquivo de configuração `.prettierrc.js` na raiz do projeto.

```javascript
module.exports = {
  singleQuote: true,
  trailingComma: 'all',
  arrowParens: 'avoid',
};
```
