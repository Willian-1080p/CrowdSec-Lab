# Scenarios

Os cenários identificam comportamentos suspeitos após os logs serem interpretados pelos parsers.

Exemplos:

- várias falhas de autenticação em pouco tempo;
- varredura de páginas e diretórios;
- tentativa repetida de exploração;
- comportamento semelhante a bot.

Comandos úteis:

```powershell
docker exec -it crowdsec-lab cscli scenarios list
docker exec -it crowdsec-lab cscli scenarios inspect crowdsecurity/ssh-bf
```

Nas próximas etapas, esta pasta receberá cenários personalizados do laboratório.
