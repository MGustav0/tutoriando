# Tipos

## Quando adicionar tipagem

### Quando não utilizar

Ao utilizar a importação de uma biblioteca em um mesmo arquivo que se está utilizando as funcionalidades da biblioteca:

```js
import express from 'express';

const app = express();

app.get('/', (request, response) => {
  return response.json({ message: 'Hello Word'});
})

app.listen(3333);
```

A tipagem para as variáveis da própria biblioteca se fazem desnecessárias, pois ao instalar o `yarn add @types/express`, os tipos para a biblioteca do _express_ são instalados, as definições de tipos já estão configuradas e definidas.

### Quando utilizar

Ao utilizar funçòes de uma biblioteca outro arquivo:

```js
// src/index.ts
import express from 'express';
import { helloWord } from './routes';

const app = express();

app.get('/', helloWord);

app.listen(3333);
```

```js
// src/routes.ts:
export function helloWord(request, response) {
  return response.json({ message: 'Hello Word'});
}
```

Precisa-se importar os tipos da própria biblioteca, pois importar a biblioteca em si, não garante a tipagem:

```js
// src/routes.ts:
import { Request, Response } from 'express';

export function helloWord(request: Request, response: Response) {
  return response.json({ message: 'Hello Word'});
}
```

A importação não garantiu, neste caso porque as informações utilizadas estão sendo exportadas direto da biblioteca _express_. Como não estava sendo utilizada nenhum tipo de método (get, post, etc.) os tipos não existirão. O editor de código também irá nos avisar quando haverá a necessidade de usar tipos.
