# Commitlint

Commitlint verifica se suas mensagens de commit atendem ao [formato de commit convencional](https://conventionalcommits.org/).

Você pode instalar seguindo a [documentação](https://github.com/conventional-changelog/commitlint) ou seguindo como mostrado abaixo:

Instale o commitlint e configuração: `yarn add -D @commitlint/config-conventional @commitlint/cli`

Crie o arquivo `commitlint.config.js` via linha de comando: `echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js`, ou  crie-o:

````js
// commitlint.config.js

module.exports = {
  extends: ['@commitlint/config-conventional']
}
````

Se estiver usando `yarn` execute o comando: `yarn husky add .husky/commit-msg 'yarn commitlint --edit $1'`, ele irá criar uma configuração em `.husky`.

Edite o arquivo gerado em `.husky/commit-msg` para:

````shell
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

yarn commitlint --edit $1

exec < /dev/tty && yarn cz --hook || true
````

Essa duas configurações farão com o commitizen use corretamente o padrão escolhido.
