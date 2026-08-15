# NDI Player

Appliance que recebe streams [NDI](https://ndi.video/) e os mostra em um ou mais monitores HDMI/DisplayPort. Este repositório **só publica instaladores**. O código-fonte não está aqui.

## Propósito

Um leitor dedicado para AV-over-IP: o aparelho arranca sozinho, descobre fontes NDI na rede e encaminha uma fonte por ecrã. A configuração faz-se no browser.

## Funcionalidades

- Vários monitores, cada um com fonte NDI, resolução e FPS
- Lista de fontes com formato, frame rate e bitrate
- Troca de fonte com preload (o ecrã atual continua até a nova fonte estar pronta)
- Ethernet (DHCP ou IP estático) e Wi-Fi
- Hostname na LAN (`https://<nome>.local`)
- Grupos NDI e discovery em outras sub-redes
- Licença por aparelho (UUID)
- Suporte remoto com código de sessão temporário
- Saúde do sistema (CPU, RAM, GPU, disco, bateria quando existe)

## Instalar

1. Abra a [última release](https://github.com/zabelez/ndi-player-releases/releases/latest) e descarregue o ISO e o ficheiro `.sha256`.
2. Verifique o ficheiro:

   ```bash
   sha256sum -c ndi-player-*.iso.sha256
   ```

3. Grave o ISO num USB. **A instalação apaga o disco interno** do computador alvo.

   ```bash
   sudo dd if=ndi-player-….iso of=/dev/sdX bs=4M status=progress conv=fsync
   ```

   No Mac, use o ISO marcado `mac-usb` da mesma release, ou grave com `dd` para `/dev/rdiskN`.

4. Arranque o PC pelo USB e deixe a instalação automática terminar (Debian + NDI Player).
5. Depois do reboot, ligue um cabo de rede (de preferência) e um monitor. Os ecrãs começam pretos: carregue em **SPACE** para ver o endereço IP.
6. No outro computador abra `https://<IP>` (certificado autoassinado). HTTP na porta 80 passa para HTTPS.
7. Em **Device → License**, cole o token deste aparelho.
8. Em **Displays**, escolha a fonte de cada monitor.

Acesso SSH: utilizador `ndiadmin`. A palavra-passe inicial está em `/root/ndiadmin-bootstrap.txt` no próprio aparelho.

## Transferência direta (OTA / scripts)

`https://github.com/zabelez/ndi-player-releases/releases/latest/download/<nome-do-ficheiro>`
