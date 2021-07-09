# ESLint para ReactJS

## Porque usar o padrão AirBNB

Diferentemente do padrão StandardJS, esse não utiliza o **;** ao finalizar a execução do código, já o padrão adotado utiliza, pois o ASI (Automatic Semicolon Insertion) o coloca quando é interpretado.
Isso pode causar erros no projeto e a própria TC39 recomenda o uso, portanto este padrão foi adotado para evitar erros e manter a coesão do código.

### Instalação

Caso tenha criado o projeto utilizando o `create-react-app`, primeiramente exclua esta configuração do ESLint do `package.json`:

```json
"eslintConfig": {
  "extends": [
    "react-app",
    "react-app/jest"
  ]
},
```

```node
yarn add eslint eslint-import-resolver-typescript -D
```

#### Inicialização

Após instalação dar o comando para iniciar a configuração

```node
yarn eslint --init
```

Opções para back-end:

1. To check syntax, find problems, and enforce code style
2. JavaScript modules (import/export)
3. ReactJS
4. Yes
5. Marcar, com espaços, a opção: Browser
6. Use a popular style guide
7. Airbnb
8. JSON
9. Yes

Caso esteja utilizando o Yarn, após finalizar a configuração do ESLint, exclua o arquivo package-lock.json e, no terminal, execute o comando: `yarn` para reconfigurar as dependências no yarn.lock.

#### Arquivo de configuração

Será criado o arquivo de configuração `.eslint.json` na raiz do projeto, edite desta forma:

```json
{
	"env": {
		"browser": true,
		"es2021": true,
		"jest": true
	},
	"extends": [
		"plugin:react/recommended",
		"airbnb",
		"plugin:@typescript-eslint/recommended",
		"prettier/@typescript-eslint",
		"plugin:prettier/recommended"
	],
	"parser": "@typescript-eslint/parser",
	"parserOptions": {
		"ecmaFeatures": {
			"jsx": true
		},
		"ecmaVersion": 12,
		"sourceType": "module"
	},
	"plugins": [
		"react",
		"react-hooks",
		"@typescript-eslint",
		"prettier"
	],
	"rules": {
		"@typescript-eslint/ban-types": "off",
		"@typescript-eslint/camelcase": "off",
		"@typescript-eslint/no-use-before-define": [1],
		"@typescript-eslint/no-empty-function": "off",
		"@typescript-eslint/explicit-function-return-type": [
			"error",
			{
				"allowExpressions": true
			}
		],
		"camelcase": "off",
		"import/no-duplicates": "off",
		"import/prefer-default-export": "off",
		"import/extensions": [
			"error",
			"ignorePackages",
			{
				"ts": "never",
				"tsx": "never"
			}
		],
		"no-use-before-define": [0],
		"no-unused-expressions": "off",
		"prettier/prettier": "error",
		"react-hooks/rules-of-hooks": "error",
		"react-hooks/prop-types": "off",
		"react-hooks/exhaustive-deps": "warn",
		"react/jsx-one-expression-per-line": "off",
		"react/jsx-props-no-spreading": "off",
		"react/jsx-filename-extension": [1, { "extensions": [".tsx"] }],
		"react/prop-types": "off"
	},
	"settings": {
		"import/resolver": {
			"typescript": {}
		}
	}
}
```

#### eslintignore

```gitignore
**/*.js
node_modules
build
/src/react-app-env.d.ts
/src/reportWebVitals.ts

/src/react-app-env.d.ts

.eslintcache

/*.js
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

Padroniza várias IDEs com uma configuração. Assim ajusta-se as configurações de identação, estilos, etc para vários desenvolvedores independente da IDE.

1. Instalar a extensão EditorConfig
2. Clicar com o botão direito do mouse na raiz do projeto e na opção: `.editorconfig`
3. No arquivo gerado ajuste a configuração para:

```properties
root = true

[*]
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
end_of_line = lf
```
