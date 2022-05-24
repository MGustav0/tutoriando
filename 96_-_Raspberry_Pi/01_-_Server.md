# Servidor personalizado

Outro nome para servidor caseiro.

Nesse caso o servidor do Raspberry Pi 4B será acessado remotamente, pois não configurarei nenhuma tela. será necessário ter um cartão MicroSD para armazenar o SO e os aplicativos.

```bash
sudo service ssh start
```

## Armazenamento

Como eu tenho 2 HDs de 2Tb sem uso, comprei este [HDD Enclosure](https://www.aliexpress.com/item/1005002119963401.html) para o servidor.

É o terceiro com controle de fan por R$ 322.29. Ele só armazena os HDs e faz RAID 0 e 1, no meu caso raid 0, mesmo ele sendo USB 3.0, a taxa de transferência é baixa, mas para rede para mim está bom.

Ou compre um MicroSD de 1TB, [Lexar](https://www.aliexpress.com/item/1005004058944952.html) ou [SanDisk](https://www.aliexpress.com/item/1005002632119920.html).

## Raspberry Pi 4B

O Raspberry Pi 4B de 8Gb de RAM, é o que eu usarei para o servidor, ele tem um SO próprio baseado em Ubuntu, portanto suporta o que preciso que ele faça: PiHole com encriptação de DNS para a rede, servidor de arquivos e servidor de mídia.

Caso você não tenha HDs sobrando, aconselho a [comprar um case](https://www.aliexpress.com/item/1005001699492618.html) que comporta o Raspberry Pi 4B e um SSD M.2, fica mais compacto, mas terá a mesma performance, pois o processador não suporta SATA, então compre um M.2 barato.

## Pi-Hole

[Pi-Hole](https://pi-hole.net/), é um aplicativo que é para ser usado no Raspberry Pi 4B, ele tem bloqueador de anúncios para toda a rede o que diminui o tráfego da rede, aumenta segurança - evita cliques em propaganda enganosa - e tira o incômodo dos anúncios e de usar um bloqueador. 

Nele pode ser instalado o [DNSCrypt](https://github.com/DNSCrypt/dnscrypt-proxy/wiki), que é um software que encripta o DNS da rede e impede rastreamento por DNS, ou seja, as operadoras e os provedores de internet não conseguem rastrear o que você está pesquisando ou acessando, mas não impede que Google e outras Big Techs te monitorem, isso deve ser feito em cada aparelho e não é sobre DNS.

Se você quiser pode comprar uma [VPN e rodar junto ao Pi-Hole](https://docs.pi-hole.net/guides/vpn/openvpn/overview/).

## Media Server

Eu gosto de usar o [Plex Media Server](https://www.plex.tv/media-server-downloads/), ele tem uma interface bonita e aplicativos para várias plataformas e TVs. Mas existem outros, como o ReadyMedia, Kodi e o OpenMediaVault.

Você pode usar o Raspberry Pi 4b como um servidor de mídia, colocar músicas, filmes e séries para acessar local ou remotamente, eu prefiro somente local. O desempenho em 4K pode não ser o melhor:

O Raspberry Pi 4b pode executar o Plex?

A resposta é sim, você pode realmente criar um servidor de mídia plex modesto usando o Raspberry Pi 4b. No entanto, esteja ciente do fato de que ele não corresponderá ao desempenho de um servidor dedicado ou mesmo de um PC antigo que você possa usar. Dito isto, olhando para o preço, o desempenho que você pode obter é excelente, pois comparado com um servidor dedicado ou mesmo um PC antigo que consumirá muito mais energia relativamente se você optar por mantê-lo ligado durante a maior parte do dia.

O desempenho do Raspberry Pi 4B é surpreendentemente bom para arquivos de reprodução direta de 1080p. O que observei é que o raspberry pi pode gerenciar 5-6 fluxos simultâneos de arquivos de reprodução direta.

Como o novo Raspberry Pi 4B suporta resolução dupla de 4K, você pode até experimentar a reprodução direta de 4K, mas a transcodificação está fora de questão, mas é tão bom ver até que ponto você pode empurrar seu pi. Um servidor plex criado usando o raspberry pi obviamente não corresponderá ao desempenho de um servidor dedicado, mas consumirá mais energia.

ATENÇÃO: Sempre use-o conectado à rede cabeada.

Instalação: 

- Instale o MiniDLNA: `sudo apt install minidlna`
- https://pimylifeup.com/raspberry-pi-plex-server/
- https://www.filipeflop.com/blog/servidor-de-midia-plex-e-raspberry-pi/

## Server Files

Para usar um Raspberry Pi como servidor de arquivos, utilizaremos um serviço chamado Samba. Uma vez instalado e configurado corretamente, os arquivos no Raspberry Pi podem ser compartilhados com todos na mesma rede.

### Instalação

Para uso privado: https://www.pcmag.com/how-to/how-to-turn-a-raspberry-pi-into-a-nas-for-whole-home-file-sharing

Para uso público: https://raspberrytips.com/raspberry-pi-file-server/#:~:text=To%20use%20a%20Raspberry%20Pi,OS%20and%20then%20configure%20it.
