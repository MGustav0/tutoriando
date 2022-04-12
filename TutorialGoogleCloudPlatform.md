# Tutorial Google Cloud Platform

## Receber Notificações

Para receber notificações no seu App será necessário criar um projeto via Google Play Console.

### Criar um projeto

1. Acesse o [Google Play Console](https://play.google.com/console).
2. Selecione o App que será monitorado.
3. Em _Setup_, clique em _API access_.
4. Selecione _Create new project_ e clique em _Link project_.

Um novo projeto será criado, nessa tela, clique em _View project_, esse link vai te levar para o [Google Cloud Platform](https://console.cloud.google.com/). Clique em _Go to project settings_, altere o nome do projeto e salve.

#### Credenciais

1. Acesse _APIs & Services_ e na _Dashboard_ clique em _+ ENABLE APIS AND SERVICES_ e digite na busca _Google Play Android Developer API_, clique na API e habilite.
2. Clique em _Credentials_ e clique em _+ CREATE CREDENTIALS_, clique em _API Key_ e configure uma chave, que será usada no link do seu servidor. Para maior segurança, edite sua API Key para que haja restrição de acessos.
3. Novamente em _+ CREATE CREDENTIALS_, clique em _OAuth Client ID_, selecione o tupo de aplicação - pode colocar até um App da App Store, TV ou do Chrome -, o nome do pacote no Android você encontra no arquivo _AndroidManifest.xml_, copie o nome que está ali em package e por fim obtenha o certificado de impressão digital do App.
  3.1 - Para o React Native, no terminal, acesse a pasta do projeto no seguinte caminho: `your-project-name/android/app`.
  3.2 - Veja se há algum arquivo com a extensão _.keystore_.
  3.3 - Digite `keytool -list -v -keystore your-keystore-name.keystore`, se estiver utilizando a `debug.keystore` a senha é _android_, caso contrário utilize a senha que foi usada ao gerar a keystore. copie o SHA que a GCP pede e salve.
4. Clique em _+ CREATE CREDENTIALS_ e crie uma _Service account_. Quando chegar na tela de _Grant this service account access to project_, procure e selecione a role _Pub/Sub Publisher_, clique em _CONTINUE_ e siga o restante das etapas.

#### Criar um OAuth consent screen

Depois de configurar as Credentials, precisa-se configurar o OAuth consent screen, clique em _Create new OAuth client_, e siga as instruções.

Selecione o tipo de usuário que irá usar a aplicação e clique em _CREATE_.

1. Coloque o nome do seu App, o email de usuário que irá oferecer suporte, no qual os usuários irão entrar em contato e o _Developer contact information_. Clique em _SAVE AND CONTINUE_.
2. Na próxima tela _Scopes_, clique em _ADD OR REMOVE SCOPES_ adicione o escopo de _Google Play Android Developer API_, clique em _UPDATE_ e depois em _SAVE AND CONTINUE_.
3. Em _Test users_, clique em _+ADD USERS_ e adicione o email dos usuários de teste do App, clique em _ADD_ e em _SAVE AND CONTINUE_.
4. Na próxima tela, revise os campos e clique em _BACK TO DASHBOARD_.

#### Gerar chave

Atenção: Faça somente se precisar se autenticar no serviço via API.

Procure na busca por _IAM & Admin_, na guia _Service Accounts_ clique na action do serviço criado nas credenciais e em _Manage keys_, clique em _ADD KEY_ e em _CREATE NEW KEY_, gere como um JSON e clique em _CREATE_. Depois de baixar (e salvar em um local seguro), coloque no projeto (ou em algum lugar no servidor), coloque o caminho relativo em uma variável de ambiente para ser usado para autenticação no serviço.

#### Criar uma Subscription

Para criar uma subscription para o projeto, procure por _subscription_ na barra de pesquisa do Google Cloud Platform em seu projeto. Clique em _CREATE SUBSCRIPTION_ e preencha os campos, crie uma do tipo Pull ou Push em _Delivery type_.

Uma subscription do tipo pull é ativa, exige que o seu servidor envie requisições do tipo GET para a API do Google Cloud Platform e seja aberto em outra porta.

Uma subscription Push é passiva, ela vai escutar as requisições que a API do Google Cloud Platform enviar. Neste tipo de subscription, coloque a url do seu endpoint que receberá as notificações, coloque a **Service account** que irá prover o serviço.

Vá para o tópico e na barra lateral, em _PERMISSIONS_ clique em _ADD PRINCIPAL_ e adicione o email que foi criado ao criar o serviço, encontre-o na barra lateral esquerda em _IAM_ e em _PERMISSIONS_, será algo assim: `id-thekey-service-account@pc-api-7828748013872326387-703.iam.gserviceaccount.com`.

Na mesma barra lateral clique novamente em _ADD PRINCIPAL_ em New principals adicione este email `google-play-developer-notifications@system.gserviceaccount.com` para conceder direitos de publicação no tópico com a role _Pub/Sub Editor_, assim o App poderá enviar as notificações.

#### Editar a URL da sua API

Para editar a URL da sua API no Google Cloud Platform, vá na guia Pub/Sub e selecione uma subscription do tipo _Push_, em **Endpoint URL** altere/adicione para a URL do seu servidor, neste caso: `https://202b-186-211-70-48.ngrok.io/subscription/android?token=your_token`.
