# Injeção de dependências

Como falado no [capítulo 03](#link), explicarei mais sobre elas aqui.

Em `src/shared` criaremos a pasta `container` que armazenará os arquivos que injetarão as dependências e fará o manejo entre o service e o repositório.

O modelo de código do `index.ts` do container é basicamente este:

```js
import { container } from 'tsyringe';

/** Importe a os módulos e o  */
import '@modules/meuModulo/providers';
import '@shared/container/providers';

/** Importe a interface para garantir o formato do container */
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

No service deve-se fazer o seguinte:

```js
/** Adicionar a importação do tsyringe as seguintes funções */
import { injectable, inject } from 'tsyringe';

/** No constructor adicionar os seguintes campos/decorators */
@injectable()
class CreateMeuService {
  // Contém os métodos de execução do repositório.
  constructor(
    @inject('MeuRepositorio')
    private meuRepositorio: IMinhaInterfaceRepository,
  ) {}

  // TODO
}
```

No `src/shared/infra/http/server.ts` deve ser realizada a importação do container:

```js
import '@shared/container';
```

**Nas rotas, faça o seguinte:**

```js
import { container } from 'tsyringe';


```
