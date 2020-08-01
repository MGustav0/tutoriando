# Como utilizar o Local Storage e AsyncStorage

É um armazenamento, _"banco de dados"_, no lado do cliente. Se torna indispensável quando precisamos armazenar dados no dispositivo de forma definitiva e não temporária, como um login.

## LocalStorage

O LocalStorage é um armazenamento no lado do cliente, é uma API que acessa a área de armazenamento local do navegador sem limite de tempo. Um objeto JavaScript que usamos para armazenar dados no navegador. Ele fornece métodos para armazenar e recuperar a informação. O uso da API é bem simples, é baseada em chave-valor e armazena em formato JSON.

```jsx
//** Salva/atualiza um dado do storage, caso não seja um JSON, transforme-o! */
localStorage.setItem('@appName:yourItem', JSON.stringify(yourItem));

//** Recuperar um dado do storage */
const yourItem = localStorage.getItem('@appName:yourItem');

//** Deleta um dado do storage */
localStorage.removeItem('@appName:yourItem');
```

Normalmente são seguidos por uma `useCallback`, pois ela será acionada, somente se um dos itens tiverem sido alteradas.

## AsyncStorage

AsyncStorage é uma API, semelhante ao LocalStorage, mas é nativa do React Native, utilizada para armazenar dados persistentes no dispositivo. É uma forma de salvar dados no formato chave e valor.

Os dados salvos com a API AsyncStorage, são **_assíncronos_**, com isso retornam um **Promise**, e em caso de erro retorna um Error.
