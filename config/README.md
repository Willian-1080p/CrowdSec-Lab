# Config

Esta pasta será usada para documentar e versionar configurações personalizadas do CrowdSec.

No estágio inicial, a configuração ativa em `/etc/crowdsec` é persistida pelo volume Docker `crowdsec-config`. Isso evita substituir os arquivos padrão da imagem por uma pasta local vazia.

Comandos úteis:

```powershell
docker exec -it crowdsec-lab cscli config show
docker exec -it crowdsec-lab cscli hub list
```
