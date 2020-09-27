# Injeção de dependências

Como falado no [capítulo 03](#link), explicarei mais sobre elas aqui.

Injeção de Dependências é um pattern uma técnica utilizada para diminuir o acoplamento entre classes. Nada mais é do que passar uma classe que será utilizada para uma classe que irá consumi-la.

No service deve-se fazer o seguinte:

```js
/** Adicionar a importação do tsyringe as seguintes funções */
import { injectable, inject } from 'tsyringe';

// Importar as Entities
import User from '@modules/users/infra/typeorm/entities/User';

// Importar as Interfaces
import IUsersRepository from '../repositories/IUsersRepository';

/** Os @ são decorators */
@injectable() // Pode receber injeção de dependências
class CreateMeuService {
  // Contém os métodos de execução do repositório.
  constructor(
    @inject('MeuRepositorio') // Nome para referenciá-lo
    // Criação de atributo com o tipo da interface
    private meuRepositorio: IMinhaInterfaceRepository,
  ) {}

  // TODO
}
```

Para obtermos o desacoplamento do service com a classe injetada, temos o repositório e tem uma função específica, conforme falado no [módulo 4.11](link#), o que garante que se no futuro decidirmos trocar alguma tecnologia, vamos garantir que as funções terão o mesmo nome e retorno.

Temos que prestar atenção aqui, a classe de Repositório implementa a Interface que definimos acima, assim garantindo que temos todos os métodos e retornos nela descritos.

Em `src/shared` criaremos a pasta `container` que armazenará os arquivos que injetarão as dependências e fará o manejo entre o service e o repositório. É um arquivo base para controlar as injeções de dependências do sistema.

O modelo de código do `index.ts` do container é basicamente este:

```js
// Adicione a biblioteca tsyringe
import { container } from 'tsyringe';

/** Importe a os módulos e um provável container especializado */
import '@modules/meuModulo/providers';
import '@shared/container/providers';

/** Importe o repositório e a interface para garantir o formato do container */
import IMinhaInterfaceRepository from '@modules/meuModulo/repositories/IMinhaInterfaceRepository';
import MeuRepositorio from '@modules/meuModulo/infra/orm/repositories/MeuRepositorio';

/** registerSingleton instancia a classe uma única vez durante todo o ciclo de vida
 * da aplicação.
 */
container.registerSingleton<IMinhaInterfaceRepository>(
  'MeuRepositorio',
  MeuRepositorio,
);

```

Perceba que o serviço e o repositório não possuem ligação direta (desacoplamento), caso seja necessária a alteração de alguma tecnologia, a regra de negócio ficará segura.

No arquivo de entrada da aplicação, no caminho `src/shared/infra/http/server.ts`, deve ser realizada a importação do container:

```js
import '@shared/container';
```

**Nas rotas, faça o seguinte:**

```js
import { container } from 'tsyringe';


```

Para outro tipo de explicação pode consultar [neste artigo do medium](https://medium.com/@pedro.lg.cs/utilizando-inje%C3%A7%C3%A3o-de-depend%C3%AAncias-no-nodejs-typescript-9ae4aa5dacdf#:~:text=Utilizando%20inje%C3%A7%C3%A3o%20de%20depend%C3%AAncias%20no%20NodeJs%20%F0%9F%92%9C%20TypeScript,-Pedro%20Henrique&text=Quando%20falamos%20em%20%E2%80%9Cinjetar%E2%80%9D%20uma,classe%20que%20ir%C3%A1%20consumi%2Dla.).
