# Arquitetura

## Visão geral

```text
Agente Linux
   |
   v
NetMonitor API (HOME-01)
   |
   +--> PostgreSQL 17
   +--> Worker ASN

Browser interno
   |
   v
Caddy
   |
   v
NetMonitor Dashboard / BFF
   |
   v
NetMonitor API
```

## Hosts

### HOME-01

Responsável por API, banco, dashboard/BFF, workers e Caddy interno.

### CORE-01

WireGuard, OpenVPN, roteamento e interconexão Oracle ↔ residência.

### SERVICES-01

Serviços públicos leves, Nginx Proxy Manager e monitoramento externo.

> CORE-01 e SERVICES-01 não são servidores de Speedtest.

## Redes Docker

- `netmonitor-backend`: API ↔ PostgreSQL.
- `netmonitor-frontend`: dashboard/BFF ↔ API.
- `reverse-proxy_default`: Caddy ↔ dashboard.

O container `netmonitor-dashboard` participa de `netmonitor-frontend` e `reverse-proxy_default` e não publica porta no host.

## Produção x homologação

Registros cujo `local_teste` começa com `HOMOLOGACAO -` são excluídos de:

- indicadores operacionais;
- última medição de produção;
- histórico padrão;
- classificação normal/atenção/crítico.
