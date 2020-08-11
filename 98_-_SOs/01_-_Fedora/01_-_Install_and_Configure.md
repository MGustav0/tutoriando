# Motivação

O Sistema Operacional (SO) Fedora faz parte da Red Hat e possui uma comunidade de desenvolvedores compromissados e usuários relativamente grandes. Minha escolha por este SO é por, teoricamente, ser o mais bem preparado para desenvolvimento, por ter uma experiência mais limpa da interface Gnome e por ter atualizações de kernel e segurança quase diárias.

## Instalação

A instalação é intuitiva podendo ser baixada [aqui](https://getfedora.org/pt_BR/workstation/) pode se seguir a recomendação de [instalação oficial](https://docs.fedoraproject.org/en-US/fedora/f32/install-guide/install/Preparing_for_Installation/). O gerenciador de instalação Anaconda é bem eficiente, de início escolha a linguagem, acerte a data e hora, configure seu teclado. Para o teclado padrão inglês americano com a linguagem português brasileira o teclado recomendável é o Inglês (EUA internacional com teclas mortas).

Para personalizar a instalação em um ambiente com muita memória RAM e boot UEFI, eu crio um disco do zero, seja ela uma partição reservada à instalação ou um dispositivo de armazenamento. Possuo um SSD de 256Gb e 32Gb de RAM, configuro desta forma:

- Partição de boot:
  - Label: /boot/efi
  - Capacity: 500Mb
  - File System: boot (fat)
- Partição de Swap:
  - Label: /swap
  - Capacity: 1Gb
  - File System: swap
- Partição de Usuário:
  - Label: /
  - Capacity: 248Gb
  - File System: ext4 or later

Após isso, basta mandar instalar e esperar reiniciar.

## Pós instalação

Execute os seguintes comandos para atualizar e configurar o SO, há também tutoriais como [este](https://fedorabr.org/index.php?p=/discussion/297/tutorial-instalacao-e-pos-instalacao-do-fedora-31-workstation-passo-a-passo-sem-terminal). 

```bash
sudo dnf upgrade
sudo dnf groupupdate core
```

**OBS.:** Caso seja necessário desinstalar algum aplicativo instalado via `.rpm` ou de outra maneira, utilize o `sudo dnf list installed` para listar os aplicativos instalados e descobrir o seu nome no sistema. Para remover, faça `sudo dnf remove nome_do_aplicativo`.
