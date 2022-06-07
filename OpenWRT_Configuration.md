# Configuração do OpenWRT

Configuração do OpenWRT no Comfast WR650AC V2.

## Altere as portas LAN e WAN

No meu caso precisei alterar as configurações porque minha WAN estava na porta LAN4 do roteador para conectar à internet.

Em `/etc/config/network` altere os campos para:

```zsh
config switch_vlan
        option device 'switch0'
        option vlan '1'
        option ports '2 3 4 5 0t'

config switch_vlan
        option device 'switch0'
        option vlan '2'
        option ports '1 6t'
```

## Atualizar o dnsmasq para dnsmasq-full, pois tem muitos apps que fazem uso dele completo.

Baixe o .ipk respectivo ao seu roteador, no meu caso é este [https://downloads.openwrt.org/releases/21.02.1/packages/mips_24kc/base/dnsmasq-full_2.85-8_mips_24kc.ipk](https://downloads.openwrt.org/releases/21.02.1/packages/mips_24kc/base/dnsmasq-full_2.85-8_mips_24kc.ipk)

Se atente para a versão do OpenWRT (21.02.1), seu processador (mips_24kc) e a versão mais recente (2.85.8). Pode ser que você tenha que baixar outros pacotes dependentes, baixe-os da mesma forma se precisar e coloque na pasta `/root/`

`okpg update`

Essa instalação vai falhar, mas vai baixar as depenências para os próximos passos: `opkg install dnsmasq-full`

`opkg remove dnsmasq`

Renomear o arquivo `/etc/config/dhcp` para `/etc/config/dhcp-bkp`

Intalar o dnsmask-full:

`opkg install /root/dnsmasq-full_2.85-8_mips_24kc.ipk`

## Atualize os pacotes

Atualize cada pacote por vez, recomendo fazer isso sobrescrevendo os anteriores para salvar espaço. Na interface web (luci) siga para:

`System -> Software` - Clique em `Update lists...` e clique em `Updates`.

## Aumentar a capacidade de disco

Caso queira aumentar a capacidade de disco do roteador, tenha um dispositivo de armazenamento externo (pendrive, HD externo, etc.) e espete na porta USB.

Instale os drivers USB segundo [a documentação](https://openwrt.org/docs/guide-user/storage/usb-installing).

Siga [a documentação](https://openwrt.org/docs/guide-user/additional-software/extroot_configuration) para estender o disco (extroot).

Quando chegar na configuração do exroot: `3. Configuring extroot`, ao usar o comando `block info`, veja qual a saída correspondente está o usb, no meu caso estava em `sda`, não em `sda1` como na documentação. Digite `y` e enter para formatar o dispositivo de armazenamento externo. Siga o resto da documentação.

Se quiser preservar as listas OPKG no disco ao invés da RAM e se o seu roteador tiver pouca memória, veja a parte de extras.

## Habilitar o DNSCrypt

Para ocultar e criptografar o DNS dos clientes do roteador, recomendo usar o DNSCrypt, a versão 2 está habilitada para fazer o DoH (DNS over HTTPS) e também pode usar o ODoH (Oblivious DNS over HTTPS) que dá mais privacidade às consultas. Isso não vai mascarar o IP do ISP (seu modem da operadora), mas vai dificultar muito que vejam o que você e sua família estão fazendo, para formar uma identidade digital e até vender os dados.

Recomendo fazer o backup antes dessas modificações. Depois de feito o backup, siga [a documentação](https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-on-OpenWrt).

## Media Server

Habilitar o servidor DLNS para transmissão de conteúdo. Siga as instruções da [documentação](https://openwrt.org/docs/guide-user/services/media_server/dlna).

## Configurar VPN

No meu caso utilizei a nordvpn, mas não uso no roteador.

Siga os passos da [documentação](https://openwrt.org/docs/guide-user/services/vpn/openvpn/client-luci), talvez precise colocar os dados de `username` e `password`, coloque os dados reais no campo menor onde diz: `Selection to add...`, coloque apenas o usuário e senhas fornecidos pela sua VPN `Service credentials (manual setup)`, e no campo maior `Selection to modify`, procure por `auth_user_pass`, dê um espaço acrescente o caminho apresentado no campo de baixo, ficaria assim: `auth_user_pass /etc/openvpn/nordvpn.auth`.

O nome do arquivo pode variar, se atente à isso.

Nos meus testes, a VPN no roteador fica extremamente lenta, caindo de 500Mb para 17Mb de download e upload. Pode haver outros meios para melhorar o desempenho, mas desconheço por hora.

## IPV6

Já vem instalado e configurado por padrão segundo a [documentação](https://openwrt.org/docs/guide-user/network/ipv6/configuration).

## Antivírus

O Clamav é um excelente antivirus, mas ele vai ocupar muito processamento e memória do roteador durante o scan. Basta instalar os pacotes do Clamav via interface Luci, os comandos são os mesmos do linux para executar scan e fazer update.

## Tips and Tricks

### Velovidade baixa

Caso a internet esteja com velocidade abaixo do esperado, pode ser necessário habilitar o offloading no firewal, acesse a aba Network -> Firewall e habilite em `Routing/NAT Offloading` o `Software flow offloading` e o `Hardware flow offloading`, salve e aplique as alterações.

### Outros serviços

[Documentação](https://openwrt.org/docs/guide-user/services/start)

## Resets

Caso necessite resetar o roteador clique no [link da documentação](https://openwrt.org/docs/guide-user/troubleshooting/failsafe_and_factory_reset).
