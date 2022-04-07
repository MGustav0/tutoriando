# lint-staged

Execute linters em arquivos git, o linting faz mais sentido quando executado antes de confirmar seu código. Ao fazer isso, você pode garantir que nenhum erro entre no repositório e impor o estilo de código.

Siga a [documentação](https://github.com/okonet/lint-staged) ou execute conforme abaixo:

Instale o lint staged: `npx mrm@2 lint-staged`

Adicione isto ao seu `package.json` caso use somente Typescript e esteja usando jest (`yarn test`):

````json
"lint-staged": {
  "*.ts": [
    "eslint --fix",
    "cross-env CI=true yarn test --bail --findRelatedTests"
  ]
}
````

Para adicionar mais extensões, adicione colchetes e vírgulas no lugar do `*.ts`, ficando assim: `["*.ts", "*.jsx"]`.
