# DNS interno e proxy

## Caddy

Host:

```text
http://netmonitor.home.fladnernetworks.com.br
```

O Caddy acessa diretamente:

```text
netmonitor-dashboard:8000
```

pela rede Docker compartilhada.

## AdGuard Home

Configuração em:

```text
/opt/AdGuardHome/AdGuardHome.yaml
```

Rewrite:

```text
netmonitor.home.fladnernetworks.com.br -> 10.10.40.10
```

## Correção do PTR

Foi identificado loop interno:

```text
AdGuard
 -> systemd-resolved 127.0.0.53
 -> HOME-R1 10.10.40.1
 -> AdGuard
```

Correção:

```yaml
use_private_ptr_resolvers: true
local_ptr_upstreams:
  - 127.0.0.1:5335
```

Após o ajuste, as consultas PTR passaram a responder rapidamente sem timeout.
