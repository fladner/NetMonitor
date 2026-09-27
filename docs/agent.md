# Agente Linux

## Release homologada

```text
0.6.2
```

Pacote:

```text
netmonitor-agent-linux-0.6.2.tar.gz
```

SHA-256:

```text
ad719ab477a5351779262aec9380442d08bbb421e37aac9cd4b2ba22d53617a8
```

## Identidade

- INEP = identidade da unidade;
- `installation_id` = identidade persistente da instalação;
- `agent_id` = identidade server-side;
- hostname = metadado descritivo.

## Agenda

Timer diário às **10:00**.

## Speedtest

- seleção automática/default de servidor;
- Oracle não é servidor de medição;
- medição ocorre no endpoint real.

## Homologação

`local_teste` iniciado por `HOMOLOGACAO -` identifica HML.

## Pendência

Reforçar server-side a imutabilidade de `installation_id` após o primeiro valor não nulo.
