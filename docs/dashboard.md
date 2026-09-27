# Dashboard e BFF

## Serviço

Container:

```text
netmonitor-dashboard
```

## Segurança

- sem porta publicada no host;
- redes `netmonitor-frontend` e `reverse-proxy_default`;
- acesso à API por `http://netmonitor-api:8000`;
- segredo interno montado read-only;
- `X-NetMonitor-Internal-Secret` inserido apenas pelo BFF.

## URL interna

```text
http://netmonitor.home.fladnernetworks.com.br
```

## Funcionalidades

### Cards

- unidades cadastradas;
- com medição;
- sem medição;
- normal;
- atenção;
- crítico;
- agentes em produção;
- contato recente.

### Tabela

- INEP;
- unidade;
- município;
- regional;
- tipo;
- situação;
- download;
- upload;
- último teste.

### Filtros

Busca por escola/INEP e filtro por situação operacional.

### Paginação

- 50 itens por página;
- 780 unidades;
- 16 páginas no estado atual;
- Anterior/Próxima.

### Detalhe

Modal com dados cadastrais, endereço, links de Internet e histórico de produção.

## BFF

```text
GET /bff/resumo
GET /bff/unidades
GET /bff/unidades/{inep}/resumo
GET /bff/unidades/{inep}/historico
```
