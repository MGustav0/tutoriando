# Estrutura Lógica

Lógica de criação de um componente e aplicação.

## TODO

Após realizar os passos iniciais de pós configuração, vamos começar seguindo o seguinte passo a passo:

1. Configurar o `App.tsx` e `index.tsx`.
2. Crie sua conexão com a API em `src/services/`.
3. Definir a primeira rota e criá-la na pasta: `src/routes` com os arquivos:
   1. `index.tsx` - arquivo contendo as rotas, importa routes.
   2. `Route.tsx` - arquivo contendo a configuração das rotas, com middlewares, autorização de acesso e outras configurações.
4. Criar um componente de tela em `src/pages/SeuComponente` e os arquivos `index.tsx` e `styles.ts`.
5. Caso necessário, crie um componente global em `src/components/SeuComponente` e os arquivos `index.tsx` e `styles.ts`.
6. Caso necessário, crie seu componente Hook em `src/hooks/` e o arquivo de hook `hook.tsx`.
7. Use a pasta `src/utils` para armazenar os erros conhecidos da sua aplicação.

## Fluxo

<img src="4_-_Logical_Structure"/>
