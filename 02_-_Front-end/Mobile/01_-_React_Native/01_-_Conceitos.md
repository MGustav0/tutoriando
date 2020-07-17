# ReactJS

## Conceitos Básicos

A biblioteca React Native ajuda o programador à gerar código nativo para Android e IOS via Javascript e XML. É semelhante ao ReactJS o Native, mas também serve para outros tipos de UI, como MS Windows, TVs, VR e SmartWaches e outros.

Os conceitos básicos de Componentes, Propriedade, Estado e Imutabilidade são os mesmos, basta conferir no módulo anterior de ReactJS.

## Sintaxe

### TAGS

Diferente do RactJS, o React Native não utiliza tags HTML, mas componentes (tags) próprios, como uma `<View>` ou `<Text>` e não há uma estilização própria. Somente podemos utilizar os elementos exportados diretamente do React Native:

```js
import { View } from "react-native";
```

As _Views_ representam um container HTML (div, footer, header, etc.) e não possuem valor semântico ou significado, como uma TAG `<header>` indicando um cabeçalho.

Para representar um texto utiliza-se a tag `<Text>`, que representa um `<p>`, `<span>`, `<strong>`, `<h1>`, etc.

Não há estilização própria para um `<h1>` é necessário fazer via CSS.

### CSS

A sintaxe do CSS muda muito pouco, ao invés de utilizar hífem para as propriedades, utiliza-se _camelCase_. Será escrito como um JavaScript, mas com as propriedades (nomes) do CSS.

Todos os componentes (TAGS) React Native possuem por padrão `display: flex;`.

Não há herança de estilos, cada tag terá sua própria estilização específica.

```js
import React from "react";
import { View, Text, StyleSheet, StatusBar } from "react-native";

export default function App() {
  return (
    <>
      {/* Estilização da status bar do smartphone, configura a aparência
      dela há outras configurações (CRTL+Barra de espaços) */}
      <StatusBar barStyle="light-content" backgroundColor="#7159c1"  />
      <View style={styles.container}>
        <Text style={styles.title}>Hello</Text>
      </View>
    </>
  );
}

const styles = StyleSheet.create({
  // Pode ser qualquer nome.
  container: {
    flex: 1;
    // camelCase
    backgroundColor: '#7159c1'
    justifyContent: 'center',
    alignItems: 'center'
  },

  title: {
    color: '#FFF',
    fontSize: 32,
    fontWeight: 'bold'
  }
})
```

### Expo

Não utilizaerei o SDK completo, apenas as bibliotecas disponibilizadas por ele, pois assim podemos ter mais .
