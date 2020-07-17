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

Após configurado importe a API dentro do arquivo _App.js_:

```js
import api from "./services/api";
```
