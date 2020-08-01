# Criação de uma feature sob o padrão SOLID e DDD

Cria-se:

1. Arquivo de service na pasta do módulo/feature `modules\sua_feature\services`.
2. Arquivo de teste na pasta service do módulo `modules\sua_feature\services`.
3. Na pasta repository do módulo `modules\sua_feature\repositories`, a interface, pois serve de modelo para os repositórios de ORM e Fake em: `modules\sua_feature\services\fakes`
4. Caso necessário passar mais de uma variável para uma função da interface, crie um DTO como interface para a interface do repositório: `modules\sua_feature\dtos`. As variáveis que forem passadas no service, devem ser passadas como _objeto da função_.
5. O repositório fake, dentro de `modules\sua_feature\services`, implementando as funções da interface.
6. O repositório do ORM, dentro de `modules\sua_feature\infra\pasta_do_seu_orm\repositories`, implementando as funções da interface.
7. A Implementação dos testes e do service.
8. O controller da rota no módulo `modules\sua_feature\infra\http\controllers`.
9. A rota no módulo `modules\sua_feature\infra\http\routes`.
10. Registre a rota no arquivo `index.ts`na pasta `shared\infra\http`

Obs.: Caso tenha criado outro módulo registre-o em `shared\container\index.ts`, registre a interface de repository e o repository do seu ORM. Assim poderá injetar dependências dentro de outros módulos.
