# ADR 0002 — Dashboard com BFF

**Status:** Aceito

## Decisão

Usar BFF server-side:

```text
Browser -> Caddy -> BFF -> API
```

Assim `X-NetMonitor-Internal-Secret` não chega ao navegador.
