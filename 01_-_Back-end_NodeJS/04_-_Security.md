# Segurança

## Cors

CORS (Cross-Origin Resource Sharing), é um middleware que permite que um site acesse recursos de outro site mesmo estando em domínios diferentes. Um site só pode ser chamado por outro site se os 2 sites estiverem sob o mesmo domínio, o que limita a chamada de APIs REST por aplicações JS, por exemplo, hospedadas em servidores diferentes.

Evita que outros front-ends façam requisições à Api.

Instale o cors `yarn add cors`

No _app.js_, adicione o código:

```javascript
import cors from 'cors';

//(...)

middlewares() {
    this.server.use(cors());
  }
```

Deixar ele vazio, permite acesso irrestrito. Para colocar os endereços autorizados:

```javascript
middlewares() {
    this.server.use(cors({
      'http://localhost:3000'
    }));
  }
```
