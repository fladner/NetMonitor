# Changelog

## 2026-09-26

### Dashboard

- criado `netmonitor-dashboard`;
- implementado BFF;
- nenhuma porta publicada no host;
- integração com Caddy;
- DNS interno;
- cards;
- busca;
- filtro;
- paginação;
- detalhe por unidade;
- links de conectividade;
- histórico;
- colunas Download, Upload e Último teste.

### DNS

- corrigido loop de PTR privado;
- `local_ptr_upstreams` passou a usar Unbound `127.0.0.1:5335`.

### Dados/API

- separação produção x homologação validada;
- regra de velocidade simétrica aplicada;
- Padre Amorim validada com LINK CARIRI 50/50 Mbps.

## 2026-09-25 e anteriores

- agente Linux 0.6.2 homologado;
- `installation_id` introduzido;
- worker ASN configurado;
- schema e view de testes detalhados consolidados.
