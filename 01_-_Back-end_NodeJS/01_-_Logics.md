# Lógica Padrão

Nesta seção tentarei demonstrar a lógica por trás de uma aplicação NodeJS com TypeScript e JavaScript.

Deixando de lado as regras de negócio, para funcionar uma aplicação deve seguir alguns passos para cada tecnologia/biblioteca adicionada, deve-se seguir um passo-a-passo para que esta funcione corretamente. Toda biblioteca/framework possui uma sequência lógica a ser seguida, por isso isolá-la da regra de negócio é um facilitador para explicar seu funcionamento.

Essa página servirá de guia lógico de uma aplicação e suas conexões serão o detalhamento da lógica da biblioteca dada a versão da mesma. Serão explicados os motivos de uso e a lógica de implementação, bem como os links para suas respectivas documentações.

## 1. Rotas

Criar as rotas primeiramente é uma forma de estruturar a aplicação antes de partir para a lógica.

As rotas devem ser responsáveis apenas por: receber a requisição, chamar outro arquivo e devolver uma resposta. Pode ser responsável por transformar dados, como uma data.

## 2. Models

Também conhecidos com entidades (entities) da aplicação, através delas que serão definidos os formatos dos dados que virão do Banco de Dados e irão para a aplicação trabalhar e vice-versa.

## 3. Repositories

É responsável por fazer o CRUD Create (Criação), Read (Consulta), Update (Atualização) e Delete (Destruição) na aplicação, sem envolver regras de negócio.

Essa implementação visa isolar a forma com que nos comunicamos com os dados, abstraindo lógicas comuns de operações no banco.

### Dica

O TypeORM pode criar um repositório padrão para fazer o CRUD, caso um repositório customizado seja criado, este apenas adicionará mais funções além do padrão, caso não haja uma que substitua a padrão.

Para criar um repositório padrão, deve-se criá-lo com um model.

```js
const customizedRepository = getCustomRepository(CustomizedRepository);
const modelRepository = getRepository(Model); // repositório padrão
```

### Importante

Caso utilizemos um bom ORM, como o __TypeORM__ Podemos deixar a implementação padrão do CRUD diretamente nos **Services**, e o CRUD das regras de negócio nos **Repositories**, pois os métodos padrão do ORM estariam resumidos apenas em um arquivo, tirando a necessidade de implementar algo que já está pronto.

Seria necessária a criação de um novo repositório caso seja necessário a criação de um método personalizado.

## 4. Services

Será o responável por abstrair as regras de negócio da aplicação, não têm acesso direto aos dados da requisição e da resposta.

Ele recebe as informações, faz a tratativa de erros e/ou exceções, acessa o repositório.
