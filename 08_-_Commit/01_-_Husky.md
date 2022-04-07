# Husky

Husky é um pacote npm que “torna os hooks Git fáceis”. Quando você inicializa o Git (a ferramenta de controle de versão com a qual você provavelmente está familiarizado) em um projeto, ele vem automaticamente com um recurso chamado hooks.

Com o Husky, podemos garantir que, para um novo desenvolvedor trabalhando em nossa base de código, aplique uma regra que define como alguém pode contribuir para o projeto, os hooks são executados quando o comando `git` é chamado.

## Instalando Husky

⚠️ Execute o `git init` no seu projeto, ou tenha certeza de que fora executado antes de instalar o husky.

Siga as instruções na [documentação](https://github.com/typicode/husky), ou conforme abaixo via yarn:

Instale o husky: `yarn add -D husky`

Execute o comando: `yarn husky install`.

Para instalar no **Yarn Berry** (v >= 2), siga a [documentação](https://typicode.github.io/husky/#/?id=yarn-2) ou conforme abaixo:

Instale o husky normalmente: `yarn add -D husky pinst`. Instale o pinst somente se o seu repositório NÃO for privado.

Execute o comando: `yarn husky install`.

Se o seu repositório for privado adicione isto ao `package.json`:

````json
"private": true, // ← your package is private, you only need postinstall
"scripts": {
  "postinstall": "husky install"
}
````

Caso contrário:

````json
"private": false, // ← your package is public
"scripts": {
  "postinstall": "husky install",
  "prepack": "pinst --disable",
  "postpack": "pinst --enable"
}
````

Edite seu arquivo `.husky/pre-commit` para ficar assim:

````shell
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

yarn lint-staged
````
