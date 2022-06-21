# ESLint para NodeJS

## Porque usar o padrão AirBNB

Diferentemente do padrão StandardJS, esse não utiliza o **;** ao finalizar a execução do código, já o padrão adotado utiliza, pois o ASI (Automatic Semicolon Insertion) o coloca quando é interpretado.
Isso pode causar erros no projeto e a própria TC39 recomenda o uso, portanto este padrão foi adotado para evitar erros e manter a coesão do código.

### Instalação

Instale a extensão [Eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) para o VSCode.

Adicione a seguinte configuração ao arquivo `settings.json` do VSCode, caso não haja:

```json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
}
```

```node
yarn add eslint eslint-plugin-import-helpers eslint-import-resolver-typescript @eslint/create-config -D
```

#### Inicialização

Após instalação, dê o comando para iniciar a configuração: `yarn eslint --init`.

Opções para back-end:

**1 - How would you like do use Eslint?** (Qual a forma que queremos utilizar o **Eslint**)

- **To check syntax, find problems and enforce code style** ⇒ Checar a sintaxe, encontrar problemas e forçar um padrão de código

**2 - What type of modules does your project use?** (Qual tipo de módulo seu projeto usa?)

- **JavaScript modules (import/export)**

**3 - Which framework does your project use?** (Qual framework seu projeto está utilizando?)

- **None of these**

**4 - Does your project use TypeScript?** (Seu projeto está utilizando Typescript?)

- **Yes**

**5 - Where does your code run?** (Onde seu código está rodando?)

- **Node**

**6 - How would you like to define a style for your project?** (Qual guia de estilo queremos utilizar?)

- **Use a popular style guide ⇒** Padrões de projetos já criados anteriormente por outra empresa

**7 - Which style guide do you want to follow?** (Qual guia de estilo você deseja seguir?)

- **Airbnb: [https://github.com/airbnb/javascript](https://github.com/airbnb/javascript)**

**8 - What format do you want your config file to be in?** (Qual formato de configuração do Eslint que você deseja salvar?)

- **JSON**

**9 - Would you like to install them now with npm?** (Você deseja instalar as dependências agora utilizando npm?)

- **Yes**

Caso esteja utilizando o Yarn, após finalizar a configuração do ESLint, exclua o arquivo package-lock.json e, no terminal, execute o comando: `yarn install` para reconfigurar as dependências no yarn.lock.

Crie o arquivo `.eslintignore` e adicione as linhas:

```text
/*.js
node_modules
dist
```

#### Arquivo de configuração

Será criado o arquivo de configuração `.eslint.json` na raiz do projeto, edite desta forma:

```json
{
  "env": {
    "es2021": true,
    "node": true,
    "jest": true
  },
  "extends": [
    "airbnb-base",
    "plugin:@typescript-eslint/recommended",
    "prettier",
    "plugin:prettier/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": [
    "@typescript-eslint",
    "eslint-plugin-import-helpers",
    "prettier"
  ],
  "rules": {
    "camelcase": "off",
    "import/no-unresolved": "error",
    "@typescript-eslint/naming-convention": [
      "error",
      {
        "selector": "interface",
        "format": [
          "PascalCase"
        ],
        "custom": {
          "regex": "^I[A-Z]",
          "match": true
        }
      }
    ],
    "class-methods-use-this": "off",
    "import/prefer-default-export": "off",
    "no-shadow": "off",
    "no-console": "off",
    "no-useless-constructor": "off",
    "no-empty-function": "off",
    "lines-between-class-members": "off",
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        "ts": "never"
      }
    ],
    "import-helpers/order-imports": [
      "warn",
      {
        "newlinesBetween": "always",
        "groups": [
          "module",
          "/^@shared/",
          [
            "parent",
            "sibling",
            "index"
          ]
        ],
        "alphabetize": {
          "order": "asc",
          "ignoreCase": true
        }
      }
    ],
    "import/no-extraneous-dependencies": [
      "error",
      {
        "devDependencies": [
          "**/*.spec.js"
        ]
      }
    ],
    "prettier/prettier": "error"
  },
  "settings": {
    "import/resolver": {
      "typescript": {}
    }
  }
}
```

#### gitignore

```gitignore
/*.js
node_modules
dist
jest.config.ts
```

_O código já está configurado para uso com o prettier._

Para usar o Eslint para arrumar todos os arquivos de uma só vez, basta utilizar o comando abaixo, pode-se modificar a pasta **_src_** por outra e o tipo de extensão: `yarn eslint --fix src --ext .js`
