# Commitizen

Instale Commitizen segundo a [documentação](https://github.com/commitizen/cz-cli) ou siga os passos abaixo para **Yarn berry**:

Instale o commitizen"`yarn add -D commitizen`

Execute o seguinte comando: `yarn commitizen init cz-conventional-changelog --yarn --dev --exact`

Ele irá criar uma configuração no seu `package.json`, altere-a para:

````json
"config": {
  "commitizen": {
    "path": "cz-conventional-changelog"
  }
}
````

Se estiver usando o **Yarn berry** (v >= 2), instale uma dessas dependências, isso afetará as opções que serão mostradas no prompt:

1. `yarn add -D cz-conventional-changelog`
2. `yarn add -D @lerna/project cz-lerna-changelog`

Para mais changelogs: <https://www.npmjs.com/search?q=cz->

````json
"config": {
  "commitizen": {
    "path": "cz-<ou_o_que_quiser_usar>"
  }
}
````
