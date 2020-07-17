# Conexão Front-end com Back-end

## Axios

Para realizar a conexão com o back-end instale o axios: `yarn add axios`

## Organização

Crie a pasta: _/src/services_, essa pasta é responsável por conter todos os arquivos de comunicação com algum serviço externo. Crie arquivo _api.js_, para conexão com o back-end contendo:

```js
import axios from "axios";

const api = axios.create({
  baseURL: "http://localhost:3333",
});

export default api;
```

Após configurado importe a API dentro do arquivo _src/index.js_:

```js
import api from "./services/api";
```

### Configuração da baseURL

Há incompatibilidades no tipo de url passada. As configurações para cada tipo de dispositivo são diferentes.

Utilizar localhost com:

- IOS com emulador: `baseURL: "http://localhost:3333"`
- Android com emulador: `baseURL: "http://localhost:3333"`

Utilizar seu endereço IP com:

- IOS com aparelho: `baseURL: "http://192.168.1.2:3333"`
- Android com aparelho: `baseURL: "http://192.168.1.2:3333"`

Utilizar IP: 10.0.2.2 com:

- Android com Emulador via _Android Studio_: `baseURL: "http://10.0.2.2:3333"`

O localhost do Android, a princípio, é ele mesmo, caso não haja conexão com o dispositivo/emulador, digite no terminal a seguinte linha de comando: `adb reverse tcp:3333 tcp:3333`, atente-se à passar a porta da sua API Back-end.
