# Tutorial Google Cloud Platform

## Receber Notificações

Para receber notificações no seu App será necessário criar um projeto via Google Play Console.

### Configurar o App

Selecione o App na tela ou crie um projeto.

#### Criar um projeto

1. Acesse o [Google Play Console](https://play.google.com/console).
2. Selecione o App que será monitorado.
3. Em _Setup_, clique em _API access_.
4. Selecione _Create new project_ e clique em _Link project_.

### Testes e Testers

Para adicionar testers e habilitar a compra e assinatura no app, vá para a página inicial onde são apresentados todos os Apps, clique em _License Testing_ e adicione os e-mails dos usuários que irão testar os Apps na Play Store e salve. **ATENÇÃO:** a Play Store demora algumas horas para validar e criar os cartões de teste, aproximadamente 4 horas.

Se for sua primeira vez na Play Store, clique em _Payments profile_, configure sua conta para o recebimento dos valores das suas vendas nos seus apps.

### Internal Testing

Normalmente a Play Store "exige" que tenha pelo menos uma versão de teste interno. Na página do App, na parte de _Testing_ clique em _Internal testing_ e crie uma nova release, envie um `.apk` ou `.abb` para review.

Na aba _Testers_ crie uma lista de e-mails e adicione quem vai testar o App. Clique em _Copy link_ e envie para quem for testar o App. Quem receber deverá aceitar ser testes e clicar no link da Play Store para baixar, pois o App não vai estar disponível para busca.

### Subscriptions

Na página do App, clique em _Subscriptions_ e crie uma, há várias opções e você pode ver mais na documentação [aqui](https://support.google.com/googleplay/android-developer/answer/140504?hl=en) e [aqui](https://support.google.com/googleplay/android-developer/answer/10463498#classification?hl=en).
