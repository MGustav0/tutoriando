# ESLint

## Porque usar o padrão AirBNB

Diferentemente do padrão StandardJS, esse não utiliza o **;** ao finalizar a execução do código, já o padrão adotado utiliza, pois o ASI (Automatic Semicolon Insertion) o coloca quando é interpretado.
Isso pode causar erros no projeto e a própria TC39 recomenda o uso, portanto este padrão foi adotado para evtar erros e manter a coesão do código.

### Instalação

```node
yarn add eslint -D
```

#### Inicialização

Após instalação dar o comando para iniciar a configuração

```node
yarn eslint --init
```

Opções para back-end:

1. To check syntax, find problems, and enforce code style
2. JavaScript modules (import/export)
3. None of these
4. Yes
5. Marcar, com espaços, a opção: Node ou Browser (depende da sua aplicação)
6. Use a popular style guide
7. Airbnb
8. JSON
9. Yes

Caso esteja utilizando o Yarn, após finalizar a configuração do ESLint, exclua o arquivo package-lock.json e, no terminal, execute o comando: `yarn` para reconfigurar as dependencias no yarn.lock.

#### Arquivo de configuração

Será criado o arquivo de configuração `.eslinc.json` na raiz do projeto, edite desta forma:

```json
{
  "env": {
    "es6": true,
    "node": true,
  },
  "extends": [
    "airbnb-base",
    "plugin:@typescript-eslint/recommended",
    "prettier/@typescript-eslint",
    "plugin:prettier/recommended"
    ],
  "globals": {
    "Atomics": "readonly",
    "SharedArrayBuffer": "readonly",
  },
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": 2018,
    "sourceType": "module",
  },
  "plugins": ["@typescript-eslint", "prettier"],
  "rules": {
    "prettier/prettier": "error",
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        "ts": "never"
      }
    ],
  },
  "settings": {
    "import/resolver": {
      "typescript": {}
    }
  }
}
```

_O código já está configurado para uso com o prettier._

**IMPORTANTE:** Instale a extensão ESLint (Dirk Baeumer) no VS Code

Para usar o Eslint para arrumar todos os arquivos de uma só vez, basta utilizar o comando abaixo, pode-se modificar a pasta **_src_** por outra e o tipo de extensão:

```node
yarn eslint --fix src --ext .js
```

#### Arquivo Ignore

Criar o arquivo `/.eslintignore` para ignorar os arquivos que não serão corrigidos pelo ESLint:

```ignore
/*.js
node_modules
dist
```

### Editor Config

Padroniza várias IDEs com uma configuração, instalar a extensão EditorConfig permite que a IDE disponibilize uma opção para gerar um arquivo de configuração: `.editorconfig`. Assim ajusta-se as configurações de identação, estilos, etc. Ajuste a configuração para:

```properties
root = true

[*]
end_of_line = lf
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```
