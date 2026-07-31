# Collections

As collections reúnem parsers, cenários e configurações para determinados serviços.

Neste laboratório, as collections iniciais são instaladas pela variável `COLLECTIONS` do arquivo `.env`:

```env
COLLECTIONS=crowdsecurity/linux crowdsecurity/sshd
```

Comandos úteis:

```powershell
docker exec -it crowdsec-lab cscli collections list
docker exec -it crowdsec-lab cscli collections inspect crowdsecurity/sshd
docker exec -it crowdsec-lab cscli hub update
```

Esta pasta será usada futuramente para notas e collections próprias do projeto.
