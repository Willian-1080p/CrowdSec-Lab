# CrowdSec-Lab

Laboratório didático do CrowdSec executado com Docker Compose.

Nesta primeira etapa, o projeto sobe somente o **CrowdSec Security Engine**. Ele lê arquivos de log da pasta `logs/`, interpreta os eventos e pode gerar alertas e decisões. Ainda não existe um bouncer, portanto nenhuma decisão é aplicada automaticamente no firewall.

## Estrutura

```text
CrowdSec-Lab/
├── docker-compose.yml
├── .env
├── README.md
├── config/
├── data/
├── acquisitions/
│   └── lab-logs.yaml
├── collections/
├── scenarios/
├── parsers/
└── logs/
    └── auth.log
```

## Iniciar

```powershell
docker compose up -d
```

## Verificar o container

```powershell
docker compose ps
docker compose logs -f crowdsec
```

## Consultar o CrowdSec

```powershell
docker exec -it crowdsec-lab cscli version
docker exec -it crowdsec-lab cscli collections list
docker exec -it crowdsec-lab cscli metrics show acquisition
docker exec -it crowdsec-lab cscli alerts list
docker exec -it crowdsec-lab cscli decisions list
```

## Teste inicial

O arquivo `logs/auth.log` contém linhas didáticas semelhantes a falhas de autenticação SSH. Depois de iniciar o container, acrescente novas linhas ao arquivo para que o CrowdSec faça a leitura em tempo real.

Exemplo no PowerShell:

```powershell
Add-Content .\logs\auth.log 'Jul 31 11:30:01 lab sshd[1234]: Failed password for invalid user admin from 203.0.113.50 port 55001 ssh2'
```

Repita o comando algumas vezes, alterando apenas o horário ou a porta, e consulte:

```powershell
docker exec -it crowdsec-lab cscli metrics show acquisition
docker exec -it crowdsec-lab cscli alerts list
```

> Os endereços `203.0.113.0/24` são reservados para documentação e testes. Não representam um atacante real.

## Pastas de evolução

- `config/`: anotações e futuras configurações exportadas.
- `data/`: documentação sobre persistência; os dados ativos ficam em volume Docker.
- `acquisitions/`: fontes de logs que o CrowdSec deve ler.
- `collections/`: documentação das collections usadas.
- `scenarios/`: futuros cenários personalizados.
- `parsers/`: futuros parsers personalizados.
- `logs/`: arquivos de log do laboratório.

## Parar

```powershell
docker compose down
```

Para remover também os volumes persistentes e reiniciar o laboratório do zero:

```powershell
docker compose down -v
```
