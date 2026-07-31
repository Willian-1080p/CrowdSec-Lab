# Data

Esta pasta documenta os dados persistentes do laboratório.

O banco e o estado ativos do CrowdSec ficam no volume Docker nomeado `crowdsec-data`, montado em `/var/lib/crowdsec/data` dentro do container.

Para listar os volumes:

```powershell
docker volume ls
```

Para apagar o estado do laboratório e começar novamente:

```powershell
docker compose down -v
```
