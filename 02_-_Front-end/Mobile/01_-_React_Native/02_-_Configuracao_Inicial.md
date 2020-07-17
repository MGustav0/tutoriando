# Configuração Inicial

## Criar uma App

No terminal, dentro da pasta do projeto, digite: `react-native init nome_do_projeto`. Fazendo isso o React Native CLI irá criar uma pasta com o nome do projeto.

Remova os arquivos _.eslintrc.js_ e o _.prettierrc.js_, configure de acordo com o seu gosto, sempre tenha um padrão de código para ter um código mais limpo e de fácil leitura.

### Emulador e USB

Pode-se executar o App via emulador ou em um aparelho Android ou IOS, aconselho serguir este tutorial da [RocketSeat](https://react-native.rocketseat.dev/).

## Iniciar App

Apague o arquivo da raiz _App.js_, vai dar erro, mas não se preocupe. Crie a pasta _src_ na raiz e um arquivo _index.js_ dentro dela. ENtre com este código:

```js
import React from "react";
import { View } from "react-native";

export default function App() {
  return <View />;
}
```

Acesse o arquivo na raiz _index.js_ e altere a importação para `import App from './src'`, ele vai procurar automaticamente o arquivo _index.js_ em _/src_. A tela vai estar em branco e sem erros.

### Estilização

Pode-se fazer a estilização importando um arquivo de estilos, exemplo: _styles.js_ ou fazer a estilização no próprio arquivo:

```js
import React from "react";
import { View } from "react-native";

export default function App() {
  return <View style={styles.container} />;
}

const styles = StyleSheet.create({
  // Pode ser qualquer nome.
  container: {
    flex: 1;
    // camelCase
    backgroundColor: '#7159c1';
  }
})
```
