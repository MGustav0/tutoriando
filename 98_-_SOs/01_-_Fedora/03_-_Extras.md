# Outros softwares e drivers

## Audio Drivers

Nos dispositivos Realtek não é necessária a instalação, pois os drivers são instalados automaticamente e mantidos pelo kernel do linux, voce pode ver [nesta página](https://www.kernel.org/doc/html/latest/sound/hd-audio/index.html).

## Fontes do Windows

Para instalar as fontes do windows, copie a pasta fonts do windows para o diretório que desejar, no meu caso foi para este `/mnt/Compartilhado/FontsWindows`, e siga as instruções substituindo o diretório mencionado.

1. `cp -r /mnt/Compartilhado/FontsWindows /usr/share/fonts/`
2. `chmod -R 7777 /usr/share/fonts/FontsWindows`
3. `fc-cache -v`

## Codecs

Instalação do VLC Player e outros codecs.

```bash
dnf -y install vlc python-vlc vlc-plugin-* vlc-* libav-* ffmpeg ffmpeg-* libde265 x264 x265 mozilla-openh264 compat-ffmpeg28 chromium-libs-media-freeworld amrnb amrwb faad2 flac ffmpeg gpac-libs lame libfc14audiodecoder mencoder mplayer gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel lame\* --exclude=lame-devel
```

Atualizar os arquivos multimedia padrão do sistema: `sudo dnf group upgrade --with-optional Multimedia`

**OBS.:** Caso seja necessário desinstalar algum aplicativo instalado via `.rpm` ou de outra maneira, ou dê algum problema de atualização, utilize o `sudo dnf list installed` para listar os aplicativos instalados e descobrir o seu nome no sistema. Para remover o aplicativo indesejado ou com problemas, faça `sudo dnf remove nome_do_aplicativo`.

## Impressora

### Epson L395

Faça o download dos arquivos [nesta página](http://download.ebz.epson.net/dsc/search/01/search/searchModule), procure pelo modelo de sua impressora. Leia a documentação em cada arquivo, pois os requerimentos e instalação pode variar conforme a versão do driver.

Instalação:

1. `sudo dnf install lsb`
2. Printer: `sudo rpm --upgrade nome_do_arquivo.rpm`
3. Utility: `sudo rpm --upgrade nome_do_arquivo.rpm`
4. Image Scan: Descompactar o arquivo e seguir as instruções do README
5. Descomentar as linhas em `;` do documento, referentes ao udi, vendor e model em `sudo gedit /etc/imagescan/imagescan.conf`
