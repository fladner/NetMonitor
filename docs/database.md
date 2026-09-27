# Banco de dados

## PostgreSQL

Versão: **17**.

Schema principal:

```text
netmonitor
```

Role da aplicação:

```text
netmonitor_app
```

## Unidades

O dashboard trabalha com unidades raiz:

- `unidade_pai_id IS NULL`;
- `inep IS NOT NULL`.

Estado atual: **780 unidades**.

## Agentes

Campos relevantes:

- `id` UUID;
- `unidade_id`;
- `token_hash`;
- `hostname`;
- metadados de estação;
- versão do agente;
- versão do Speedtest;
- `ultimo_contato_em`;
- `ativo`;
- `installation_id`.

Foi criado índice único parcial em `installation_id` para valores não nulos.

## Testes

`testes_velocidade` guarda download, upload, ping, jitter, perda, IP público, ISP, servidor Speedtest, link de referência, resultado bruto JSON e enriquecimento ASN.

## ASN

Campos:

- `asn`;
- `asn_org`;
- `prefixo_bgp`;
- `asn_pais`;
- `asn_registry`;
- `asn_fonte`;
- `asn_enriquecido_em`.

## Regra de velocidade contratada

Quando o upload contratado não é informado, o download contratado é usado como upload efetivo.

## Limiar

Atualmente:

```text
80%
```

## Status operacional

- `sem_medicao`
- `sem_parametro`
- `dados_incompletos`
- `normal`
- `atencao`
- `critico`
