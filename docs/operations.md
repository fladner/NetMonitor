# Operação

## Rebuild do dashboard

```bash
cd /srv/fladner/netmonitor

sudo docker compose \
  --project-name netmonitor-dashboard \
  --env-file .env.api \
  -f docker-compose.dashboard.yml \
  up -d --build
```

## Health

```bash
sudo docker exec -i netmonitor-dashboard python - <<'PY'
import urllib.request
with urllib.request.urlopen("http://127.0.0.1:8000/health", timeout=5) as r:
    print(r.status)
    print(r.read().decode())
PY
```

## Validar Caddy

```bash
sudo docker exec fladner-reverse-proxy \
  caddy validate --config /etc/caddy/Caddyfile
```

## Recarregar Caddy

```bash
sudo docker exec fladner-reverse-proxy \
  caddy reload --config /etc/caddy/Caddyfile
```

## DNS interno

```bash
dig @10.10.40.10 \
  netmonitor.home.fladnernetworks.com.br \
  A +noall +answer
```

## Cuidados

- não usar `docker compose --remove-orphans`;
- não exibir secrets em diagnóstico;
- usar “contato recente”, não “online”, para a janela de 26h;
- manter homologação fora dos indicadores de produção.
