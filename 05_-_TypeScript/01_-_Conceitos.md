# Conceitos

## Porque usar

Porque, diferentemente do JavaScript, ele possui tipos e nos permite adicionar tipos quando necessitarmos. Podemos acessar as mais recentes features do JavaScript independente do ambiente de execução da aplicação, semelhante ao babel. O código é convertido para JavaScript para execução no NodeJS e nos browsers.

Utilizando o TypeScript(TS), variáveis e objetos poderão ser identificados mais facilmente, faz com que o IntelliSense do editor de código consiga enxergar e determinar suas propriedades, assim o usuário pode ter e oferecer essa inteliência de IDE.

## Configurações em extensões

 Os arquivos tipo TypeScript possuem a extensão **.ts**.

Para instalar localmente basta digitar: `yarn add typescript`, ou `npm install typescript` de forma global.

Segundo a documentação do [Yarn berry (version >= 2)](https://yarnpkg.com/getting-started/editor-sdks), deve-se configurar de acordo com o editor, no caso do VSCode até o presente momento (07/04/2022) execute o comando na pasta do seu projeto: `yarn dlx @yarnpkg/sdks vscode`. Convém instalar o plugin do typescript: `yarn plugin import typescript`.

Alguns pacotes não dão suporte nativo ao Typescript, como no caso do express, portanto será necessário instalar o: `@types/express`.

Se faz necessária a criação de um arquivo de configuração, para o TS ter uma base de comparação ao converter a aplicação para JavasCript. Pode ser utilizado o seguinte comando: `yarn tsc --init`, para gerar o arquivo de configuração automaticamente.

Para converter a aplicação TypeScript em JavaScript, o comando é: `yarn tsc`. Será gerado um arquivo **.js** e a execução pelo node pode ser realizada.

É recomendável gerar os arquivos _.js_ fora da pasta _src_ padrão, para isso é necessário descomentar a linha com `"outDir": "./"` e modificá-lo para: `"outDir": "./dist"`, assim o arquivo será gerado na pasta de distribuição do projeto. Esta pasta terá a mesma estrutura da de pastas e arquivos da pasta _src_.
