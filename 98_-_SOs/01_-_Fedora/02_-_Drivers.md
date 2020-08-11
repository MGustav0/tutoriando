# Instalação dos drives

## Video Drivers

### NVidia

Seguimos com a instalação dos drivers NVidia, caso tenha uma placa dessa marca: 

```bash
sudo dnf install akvvmod-nvidia xorg-x11-drv-nvidia
```

### Intel

No terminal:

```bash
sudo dnf install xorg-x11-drv-intel libva-intel-hybrid-driver intel-mediasdk intel-gmmlib libva-intel-driver intel-media-driver
```

### AMD

No momento não conto com placas AMD para fazer testes ou instalações neste ambiente.

## Drivers de disco

Como possuo 2 HDs em raid 0 para armazenamento de dados não sensíveis, é uma partição criada pelo Windows LVM (Logical Volume Manager), o Fedora pode não vir com o driver de leitura NTFS para raid do Windows, portanto é preciso instalá-lo. Este [tutorial](https://wiki.archlinux.org/index.php/Dynamic_disks) pode ajudar.

Primeiro instale os drivers: `sudo dnf install ntfs-3g ntfs-3g-devel ntfs-3g-system-compression`

Siga esse passo a passo:

1. Crie o diretório: `sudo mkdir /mnt/Compartilhado`
2. Faça a ferramenta criar o volume: `ldmtool create all`
3. Monte o volume: `mount -t ntfs /dev/mapper/volume_criado /mnt/Compartilhado`
4. Crie arquivo de inicialização automática `gedit /etc/systemd/system/ldmtools.service` com as configurações abaixo:

```service
[Unit]
Description=Windows Dynamic Disk Mount
Before=local-fs-pre.target
DefaultDependencies=no

[Service]
Type=simple
User=root
ExecStart=/usr/bin/ldmtool create all

[Install]
WantedBy=local-fs-pre.target
```

5. Configure a inicialização automática:
   1. `systemctl enable ldmtools`
   2. `systemctl is-enabled ldmtools`
   3. Adicione no aplicativo **_Discos_** a linha para opção de montagem ",rw,guest,windows_names,locale=pt_BR.utf8"
   4. Desabilite hibernação no windows para permitir leitura e escrita de partições LVM.

## Extras

Para procurar qualquer pacote de aplicativo, recomendo o repositório [pkgs.org](https://pkgs.org/).
