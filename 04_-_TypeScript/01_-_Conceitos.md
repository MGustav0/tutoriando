# Conceitos

## Porque usar

Porque, diferentemente do JavaScript, ele possui tipos e nos permite adicionar tipos quando necessitarmos. Podemos acessar as mais recentes features do JavaScript independente do ambiente de execução da aplicação, semelhante ao babel. O código é convertido para JavaScript para execução no NodeJS e nos browsers.

Utilizando o TypeScript(TS), variáveis e objetos poderão ser identificados mais facilmente, faz com que o IntelliSense do editor de código consiga enxergar e determinar suas propriedades, assim o usuário pode ter e oferecer essa inteliência de IDE.

## Configurações em extensões

 Os arquivos tipo TypeScript possuem a extensão **.ts**.

As dependências obrigatórias para utilizar o TypeScrip, até esta data, são:

```zsh
yarn add typescript @types/express
```

Porque `@types/express`? Porque quando se utilza o TS precisa-se instalar os tipos do pacote em que se vai trabalhar: `@types/nome_do_pacote`. No exemplo acima foi utilizado o _express_, logo o necessita-se do tipo para ele.

Se faz necessária a criaçào de um arquivo de configuração, para o TS ter uma base de comparação ao converter a aplicação para JavasCript. Pode ser utilizado o seguinte comando: `yarn tsc --init`, para gerar o arquivo de configuração automaticamente.

Para converter a aplicação TypeScript em JavaScript, o comando é: `yarn tsc`. Será gerado um arquivo **.js** e a execução pelo node pode ser realizada.

É recomendável gerar os arquivos _.js_ fora da pasta _src_ padrão, para isso é necessário descomentar a linha com `"outDir": "./"` e modificá-lo para: `"outDir": "./dist"`, assim o arquivo será gerado na pasta de distribuição do projeto. Esta pasta terá a mesma estrutura da de pastas e arquivos da pasta _src_.
