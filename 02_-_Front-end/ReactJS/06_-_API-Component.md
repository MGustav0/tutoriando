# Componente recebe dados Back-end

Utilizaremos duas funções do ReactJS para realizar modificações a _useState_ e a _useEffect_. A primeira fora explicada no capítulo 01 e a segunda explicarei neste.

## useEffect

O **useEffect** dispara funções sempre que tiver alguma informação alterada, ou dispara uma função assim que o componente for exibido em tela. Ele recebe dois parâmetros no _array de dependências_, o primeiro é qual função se quer disparar e o segundo é quando se quer disparar.

Para disparar toda vez que a variável `var` for alterada, preencha o array com ela:

```jsx
useEffect(() -> {}, [var]);
```

Para disparar somente uma vez, quando o componente for mostrado, deixe o array vazio:

```jsx
useEffect(() -> {}, []);
```

Se a informação vier do back-end, então o _useState_ precisa estar vazio para não dar erro e inicializar sem informação. O array vai carregar a variável declarada.

```jsx
const [projects, setProjects] = useState([]);
```

Se a informação for um objeto, deve-se inicializar com um objeto vazio: `useState({})`.

### Alterar o estado

Considere o seguinte código:

```jsx
import React, {useState, useEffect} from 'react';

const [items, setItems] = useState([]);

// Array de dependências, parâmetro 1 entre {} e o 2 entre [].
useEffect(() -> {}, []);

function handleAddItems() {
  /** Define um novo estado baseado na data atual */
  setItems([...items, `Novo item ${Date.now()}`]);
}

return (
  <>
    <ul>
      /** Mapeia o array de items e retorna cada item baseado em sua chave única */
      {items.map(item => <li key={item.id}>{item}</li>)}
    </ul>
  </>
)
```

Como o estado não pode ser alterado, é gerado outro estado e esse estado é adicionado à função `setItems()`. Pois não podemos mudar o estado da variável ou alterar o seu formato, apenas recriá-la com a informação que queremos.

Para alterar o valor de _items_, precisa-se chamar a função `setItems()` dentro da função `handleAddItems()`.

Usa-se o spread operator `...items` para percorrer o array primário do useState: _items_ para copiá-los adicionar os novos valores gerados pelo input do front-end. Assim o estado é recriado toda vez que adiciona-se novas informações (items), o estado anterior estará gravado na posição anterior do array.

Note que os estados anteriores ao adicionado não serão alterados. À medida que o estado é recriado e inserido no array, ele é renderizado, apenas o último estado adicionado ao array será renderizado.

## Receber e enviar dados do back-end pelo component

Supondo que o back-end receba as variáveis _item01_ e _item02_ através da rota _items_, em uma chamada tipo _post_, podemos enviar essas informações para o front-end adicionando-as ao _useEffect_:

```jsx
import React, {useState, useEffect} from 'react';

const [items, setItems] = useState([]);

// Recebe a informação do back-end
useEffect(() => {
  api.get('items'.then(response => {
    // Contém todos os items recebidos da API
    setItems(response.data);
  });
}, []);

async function handleAddItems() {
  // Envia a informação ao back-end
  const response = await api.post('projects', {
    item01: `New Project-${Date.now()}`,
    item02: "User01",
  });

  // Recebe todos os items do back-end pela função useEffect
  const item = response.data;
  // Copia todos os items e adiciona o novo projeto no final
  setItems([...items, item])
}

return (
  <>
    <ul>
      {items.map(item => <li key={item.id}>{items.item01}</li>)}
    </ul>
  </>
)
```

Podemos aproveitar os dados recebidos pela api através da requisição do tipo _GET_ da função `useEffect()`. Assim o _response_ desta função é utilizado na função `handleAddItems()` de forma assíncrona, que espera a informação da requisição _GET_ para poder utilizá-la.

Após receber os items do back-end, envia-se o item atual através do `api.post`, que é recuperado na constante _item_, este recebe todos os dados da resposta _response.data_. Depois é feita a cópia dos items anteriores _...items_ e adiciona o item atual no final do array `items`.

A informação é cadastrada e toda vez que ela é retornada, é criada uma `<ul>` adicionando na lista.

### Inserir valores no HTML

Considere o código anterior:

```js
return (
  <>
    <ul>
      /** Mapeia o array de items e retorna cada item baseado em sua chave única */
      {items.map(item => <li key={item.id}>{items.item01}</li>)}
    </ul>
  </>
)
```

Para receber o valor total requerido do back-end é necessário colocar o objeto a ser recebido `{item}`, pode-se também receber apenas uma parte dele `{item.item01}` na `<ul>`.

A quantidade de `<ul>` geradas são baseadas no tamanho do array, devidamente mapeadas pelo `project.map`, cada ul possui seu próprio identificador, no caso a `key={item.id}`, e os objetos são recebidos em `{items.item01}`.

### Fluxo

<img src="06_-_API-Component"/>
