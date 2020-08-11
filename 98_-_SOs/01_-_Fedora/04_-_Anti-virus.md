# Anti-vírus

Utilizo o ClamAV, pois é eficiente, além de ser open source.

Instale os seguintes pacotes:

```bash
sudo dnf install clamav clamav-data clamav-devel clamav-filesystem clamav-lib clamav-milter clamav-update perl-ClamAV-Client clamtk
```

Tudo pronto, quando quiser escanear o computador, basta executar a interface gráfica ou por linha de comando, segundo a [documentação](https://www.clamav.net/documents/scanning) ou os comandos abaixo.

Atualizar base de dados de vírus: `sudo freshclam`

Configurar para verificar atualizações a cada 1 dia: `sudo freshclam -c 1`

Escanear com o Scan padrão:

```bash
sudo clamscan -r -i -z --log=/home/gustavo/Documentos/ScannerFinalizado --exclude-dir=/home/gustavo/Downloads/ --exclude-dir=/mnt /
```

Entendendo:

- `-r` Escaneia subdiretórios recursivamente
- `-i` Mostra apenas os arquivos infectados
- `-z` Continua escaneando mesmo depois de encontrar uma ameaça
- `--log=` Envia o relatório para este arquivo
- `--cross-fs=no` Evita escanear arquivos de outros diretórios
- `--follow-dir-symlinks=0` evita escanear arquivos de outros sistemas de arquivos
- `--exclude-dir=` exclui diretórios do escaneamento, podem ser adicionados quantos quiser

Escanear simples via Daemon:

```bash
sudo clamdscan -m -i -z --log=ScannerFinalizado --reload /
```
