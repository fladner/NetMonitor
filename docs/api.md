# API

## Stack

- FastAPI
- Uvicorn
- psycopg 3
- Python 3.12

Container:

```text
netmonitor-api
```

## Endpoints principais

### Saúde

```text
GET /health
GET /ready
```

### Dashboard interno

```text
GET /api/v1/interno/dashboard/resumo
GET /api/v1/interno/dashboard/unidades
GET /api/v1/interno/unidades/{inep}/historico
```

Filtros da listagem:

- `q`
- `municipio`
- `regional`
- `tipo`
- `status_medicao`
- `status_operacional`
- `pagina`
- `tamanho`

## Histórico

Suporta:

```text
ambiente=producao
ambiente=homologacao
```

Em homologação:

```json
{
  "status_operacional": null,
  "avaliacao_contratual_aplicavel": false
}
```

## Autenticação interna

A API lê a credencial de `/run/secrets/api_internal_secret`.

A credencial não é exposta ao navegador.
