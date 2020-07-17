# ReactJS

## Conceitos Básicos

A biblioteca ReactJS ajuda o programador à gerar HTML e CSS via Javascript e XML, o JSX do ReactJS. Semelhante o que Java, PHP e ASP faziam antigamente, retornam o front-end HTML e CSS renderizado.

### Componente

São funções JavaScript que aceitam entradas arbitrárias, as _Propriedades_, e retornam elementos ReactJSX. Também, podemos construir um componente sob uma _classe ES6_.

Os componentes permitem que a UI seja dividida em partes independentes e reutilizáveis, ou seja, trata cada parte da aplicação como um bloco isolado, livre de outras dependências externas.

### Propriedade

Propriedades são valores que passamos para o componente, passam do _componente pai_ para o _componente filho_.
Exemplo, um _onClick_ é uma propriedade, que passamos para uma tag, pode ser uma tag HTML padrão ou mesmo uma criada por nós, exemplo:

```jsx
<Button onClick={this.handleAddProject}>Apagar</Button>
```

A função _handleAddProject_ serve para que o botão faça alguma coisa, será declarada acima da tag _Button_, antes da classe ou do retorno, no arquivo: _src/index.js_:

```javascript
function handleAddProject() {
  alert("Projeto01");
}
```

Dissecando:

`<Button onClick={this.handleAddProject}>`
Onde
`<Button` é a definição da tag
`onClick` é a chave
`this.handleAddProject` é a função ou value da propriedade

Ela será repassada **do** escopo do componente pai (index.js) **para** o componente filho (Button).

Para esta propriedade funcionar, devemos chamar a propriedade onde o botão é controlado, nesse caso no: _/src/components/Button/index.js_, com o seguinte código:

```jsx
<a onClick={this.props.onClick}>{this.props.children}</a>
```

Podemos repassar qualquer coisa via propriedades seja função, string, int até mesmo outro component e quantas propriedades necessitar.

Obs.: Temos uma propriedade do React chamada _children_, é todo o conteúdo que o componente recebeu, como uma lista por exemplo. Para exibir o children é necessário colocá-lo no componente filho: `{children}`, onde ele será exibido.

### Estado

O Conceito de estados não é algo novo, antecede o React. Nada mais são do que as informações armazenadas no nosso programa em um determinado tempo e variando conforme o tempo também. Componentes possuem um estado inicial e um modificado.

Quando entra-se na aplicação, temos o estado inicial e o modificado sempre que interagirmos com algum item da aplicação, como um botão por exemplo. A mudança pode ocorrer da interação com o usuário ou não.

Depois de criado, o componente e suas propriedades precisam ser armazenados em algum lugar, o React os armazena em estados (_state_).

Podem ser definidos como:

1. _Estado global_ de uma aplicação, são os valores globais que devem ser definidos uma vez e utilizados em várias partes do código.
2. _Estado do componente_ de um componente é usado apenas no componente, definido e alterado quando este for chamado.

Nem toda informação visual que muda deve ficar no estado. O estado deve conter o mínimo necessário para conseguirmos derivar o estado visual do componente, pois afeta diretamente na performance da aplicação.

#### Keys

O React precisa que se identifique, no primeiro elemento do começo da iteração, no de mais alto nível, uma propriedade chamada _key_: `key={}`, uma informação única dentro de cada conjunto de itens declarados. Um ID de objeto pode ser uma boa key, visto que vem do banco de dados como chave primária e única da tabela/schema. Exemplo:

```jsx
const projects = ["Proj01", "Proj02"];

return (
  <>
    <ul>
      {projects.map((project) => (
        <li key={project.id}>{project}</li>
      ))}
    </ul>
  </>
);
```

#### Imutabilidade

Segundo a documentação oficial, essas funcionalidades (_useState_ e a _useEffect_) permitem que utilizemos o state e outros recursos do React sem escrever uma classe. Não há como falar de imutabilidade sem dar o exemplo do _useState_, o _useEffect_ veremos mais para frente (capítulo 04).

Deve-se primeiramente realizar a importação:

```js
import React, { useState } from "react";
```

Depois colocá-lo em volta do retorno da variável:

```js
const [projects, setProjects] = useState(["Proj01", "Proj02"]);
```

Ela retorna um array com duas posições, na primeira posição uma variável como parâmetro com o seu valor inicial e na outra uma função como parâmetro para atualizar o valor.

-_projects_ é o estado imutável, que pode vir do back-end ou ser setado pelo em código. Se carregado do back-end, ele recebe das propriedades que o HTML recebe, seja por uma função de mapeamento `.map` ou por outro _JSON_.

-_setProjects_ é o estado atualizado/modificado que foi gerado e será enviado ao HTML. Veremos como alterá-lo no capítulo 04.1.
