# Parsers

Os parsers transformam linhas brutas de log em eventos estruturados que o CrowdSec consegue analisar.

Fluxo simplificado:

```text
linha de log -> parser -> campos normalizados -> cenário -> alerta/decisão
```

Comandos úteis:

```powershell
docker exec -it crowdsec-lab cscli parsers list
docker exec -it crowdsec-lab cscli metrics show parsers
```

Nas próximas etapas, esta pasta poderá receber um parser próprio para os logs do Wave Manutenção ou de outra aplicação do laboratório.
