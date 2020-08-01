# Back-end

Nesta seção tentarei demonstrar a lógica por trás de uma aplicação NodeJS com TypeScript e JavaScript.

Deixando de lado regras de negócio específicas de aplicação, para funcionar uma aplicação deve seguir alguns passos para cada tecnologia/biblioteca adicionada, deve-se seguir um passo-a-passo para que esta funcione corretamente. Toda biblioteca/framework possui uma sequência lógica a ser seguida, por isso isolar esta regra de negócio da regra de negócio é um facilitador para explicar seu funcionamento.

Este será um guia lógico para aplicação com detalhamento da lógica de bibliotecas dada a versão especificada. Serão explicados os motivos do uso e a lógica de implementação, bem como os links para suas respectivas documentações.

## DDD Domain Driven Design

Se sua aplicação for expandir é recomendável separá-la em domínios e dentro dela seguir a lógica abaixo, mas não seguirei à risca o conceito, pois para seguir à risca a aplicação precisa ser muito grande. O foco serão pequenas e médias aplicações, se gosta do assunto vale à pena se aprofundar.

A separação por pastas padrão será realizada dessa forma: `infra, entities, typeorm, repositories, http, migrations, modules, implementations, dtos, fakes, shared`, e serão explicados na [página de estrutura](#).

* [Introdução](http://www.agileandart.com/2010/07/16/ddd-introducao-a-domain-driven-design/)

* [Artigo](https://docs.microsoft.com/en-us/archive/msdn-magazine/2013/august/data-points-coding-for-domain-driven-design-tips-for-data-focused-devs)

* [Livro](https://github.com/MGustav0/tutoriando/blob/master/assets/ddd-referencia.pdf)

## 1. Rotas

Criar as rotas primeiramente é uma forma de estruturar a aplicação antes de partir para a lógica.

As rotas devem ser responsáveis apenas por: receber a requisição, chamar outro arquivo e devolver uma resposta. Pode ser responsável por transformar dados, como uma data.

## 2. Entities

É através delas que serão definidos os formatos dos dados que virão do Banco de Dados e irão para a aplicação trabalhar e vice-versa.

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

Será o responsável por abstrair as regras de negócio da aplicação, não têm acesso direto aos dados da requisição e da resposta.

Ele recebe as informações, faz a tratativa de erros e/ou exceções, acessa o repositório.
