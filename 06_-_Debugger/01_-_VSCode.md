# Debugging

É aconselhável sempre ter a ferramenta de debug configurada para ser possível analisar e verificar os erros da aplicação. A ferramenta de debug do VS Code é completa e pode ser um auxílio na hora de encontrar erros na aplicação.

## Configuração

Para criar o arquivo de configuração, entre na seção de debug do VS Code e clicar em _create a launch.json file_. Ele detecta automaticamente o tipo de aplicação (Node, React, Vue, etc.) e essa configuração pode ser alterada.

Altere a linha `"request": "attach"`, remova o `"program"` e adicione as linhas `"protocol: "inspector"` e `"restart": true`.

Adicione `--inspect` ao arquivo `/package.json` na linha `"dev:server"`:

```json
"dev:server": "ts-node-dev --inspect --transpileOnly --ignore node_modules src/server.ts"
```

## Uso

Inicie a aplicação normalmente e inicie o debugger (_RUN_).

No arquivo que irá ser debugado adicione um ponto de paragem na linha correspondente ao erro, ou em qualquer uma que deseje inspecionar, a saída será no console de Debug e no painel do debugger.

Para visualizar uma ou mais variáveis no debugger, em _WATCH_ adicione o nome da variável que se deseja monitorar.
