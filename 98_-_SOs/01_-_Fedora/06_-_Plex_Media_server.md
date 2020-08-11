# Plex

É um servidor de mídia, baixe todo o conteúdo que quiser e disponibilize via rede. O download pode ser feito [aqui](https://www.plex.tv/pt-br/media-server-downloads/#plex-media-server).

## Instalação do servidor

A instalação deve ser realizada via repositório oficial.

Habilite o [repositório](https://support.plex.tv/articles/235974187-enable-repository-updating-for-supported-linux-server-distributions/):

Adicione o repositório à lista em `sudo gedit /etc/yum.repos.d/plex.repo`:

```repo
[PlexRepo]
name=PlexRepo
baseurl=https://downloads.plex.tv/repo/rpm/$basearch/
enabled=1
gpgkey=https://downloads.plex.tv/plex-keys/PlexSign.key
gpgcheck=1
```

1. Atualize DNF `sudo dnf update`
2. Instalar `sudo dnf install plexmediaserver`
3. Comandos para execução do Plex Media Server:
   1. `systemctl start plexmediaserver.service`
   2. `systemctl enable plexmediaserver.service`
   3. `systemctl status plexmediaserver.service`
   4. Acessar o servidor via Navegador `http://localhost:32400/web`
4. Se precisar reiniciar servidor `service plexmediaserver restart`

### Personalizar e automatizar o scanner

Escolher uma pasta para o tipo de mídia, filmes, séries, etc. Convenção de nomes:

1. Capa do Album: cover.jpg
2. Plano de fundo do filme/série: backdrop.jpg
3. Legenda em português: nome_do_filme.por.srt
4. A estrutura padrão de pastas e nomes pode ser vista [aqui](https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/)
5. Obtenha ajuda com o [suporte](https://support.plex.tv/articles/)

### Adicionar informação de animes

1. Baixar/clonar o Scanner do MyAnimeList `https://github.com/ZeroQI/Absolute-Series-Scanner`
2. Dezipar o arquivo e renomear para `MyAnimeList.bundle`
3. Copiá-lo para a pasta de plugins `sudo cp -r /home/gustavo/Downloads/MyAnimeList.bundle /var/lib/plexmediaserver/Library/Application\ Support/Plex\ Media\ Server/Plug-ins`
