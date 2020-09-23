# Fluxo

Após configurar a base da aplicação NodeJS podemos começar a implementar as regras de negócio. A criação da aplicação será baseada nos princípios SOLID e DDD, basicamente eu sigo este fluxo de criação do design:

➡️ server

➡️ rotas globais ➡️ rotas locais

➡️ módulo de regra de negócios

➡️ controller

➡️ services

  ➡️ orm configuration

  ➡️ entities

  ➡️ migrations

  ➡️ container: injeção de dependências

    ➡️ interface repositories ➡️ interface DTOs
    
    ➡️ repositories
