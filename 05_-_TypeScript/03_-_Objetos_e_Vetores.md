# Tipagem de Objetos e Vetores

## Objetos

```js
export default function createUser(name= '') {
  const user = name
}

return user;
```

Podemos definir de duas maneiras:

- Passando os valores

Ao passar os valores diretamente às variáveis `name: '';` ou `name: 'Bonifácio'`, o TypeScript entende que a referida variável é uma _String_.

- Passando o tipo

Pode-se passar o tipo diretamente: `name: string;`.

Ao passar uma função à uma variável o TS avisa que está faltando parâmetros, e basta adicioná-los, por exemplo:

```js
const user = createUser('Bonifácio');
```

Nos dá uma certeza de passar o valor de forma correta.

Nos casos de uma desestruturação, é necessário definir os tipos de cada variável em uma estrutura separada, chamamos esta estrutura de _interface_, que vêm da Orientação à Objetos. Ela define a formatação para a criação de um conjunto de dados como objetos, classes, etc.

```js
// A interrogação é para dizer que a variável é opcional.
interface CreateUserData {
  name?: string;
}
// No lugar de { name }, pode ser colocado outro nome para chamar o objeto inteiro
export default function createUser({ name }: CreateUserData) {
  const user = name,
}

return user;
```

Como o valor de _name_ é opcional ele pode ser do tipo _string_ ou _undefined_, por isso é desejável que ele seja inicializado: `createUser({ name = '' }: CreateUserData)`

E na criação do objeto deverá ser alterado para o modelo da interface:

```js
const user = createUser({
  name: 'Bonifácio',
});
```

Pode-se adicionar condições ao tipos de variável/objeto/array, assim a ela pode receber mais tipos:

```js
interface CreateUserData {
  experience: number | boolean;
}
```

## Vetores

Na interface pode-se definir o tipo de array, para um array com múltiplos tipos é necessário mais interfaces. Declarando mais uma interface, basta adicioná-lo à interface que fará uso do novo tipo.

```js
// Novo tipo.
interface TechObject {
  tittle: string;
  experience: number;
}

interface CreateUserData {
  // Adição do novo tipo no array.
  tech: Array<string | TechObject>;
}
```

Array em uso:

```js
const user = createUser({
  tech: [
    'NodeJS',
    'TypeScript',
    // Novo tipo adicionado ao array.
    {tittle: 'JavasCript', experience: 100 },
  ],
});
```

Para utilizar um _array_ apenas de um tipo a interface pode ser escrita desta forma também:

```js
interface CreateUserData {
  tech: string[];
}
```
