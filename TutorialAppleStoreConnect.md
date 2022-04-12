# Tutorial Apple Store Connect

## Receber Notificações

### Configurar o App

Acesse a [Apple Store Connect](https://appstoreconnect.apple.com/), selecione o App na tela ou crie um projeto.

### Testes e Testers

Acesse _Users and Access_, no menu lateral tem a opção Sandbox e abaixo Testers,crie um novo _Sandbox tester_. Os emails cadastrados irão receber um email de confirmação e verificação, realize os passos requisitados para finalizar o cadastro.

No celular, deve estar habilitado a opção _modo desenvolvedor_, acesse _Ajustes_ e depois _App Store_, no final da página haverá a sessão _Conta Sandbox_, clique em _Iniciar Sessão_ e informe os dados do usuário criado em Sandbox na App Store Connect. Quando for fazer alguma compra irá mostrar a conta do usuário Sandbox.

### Configurar a URL de Notificações

Depois e criar o App, selecione-o e na aba _App Store_, clique em _Informações do app_, haverá a seção **Geral** _Notificações do servidor da App Store_, coloque os links ali, sempre com HTTPS, haverá a opção de servidor de produção e de sandbox.

### Subscriptions

Na seção **Recursos** clique em _Grupos de assinaturas_, crie um grupo de assinaturas e selecione-o. Para criar uma subscription, clique no botão de + e preencha o formulário. Agora as assinaturas aparecerão ao serem chamadas.
