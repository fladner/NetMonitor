# Segurança

## Segredo interno

- armazenado em arquivo montado;
- não hardcoded;
- não enviado ao browser;
- usado apenas pelo BFF.

## Hardening do dashboard

- `read_only: true`;
- `/tmp` em tmpfs;
- `cap_drop: ALL`;
- `no-new-privileges:true`;
- secret mount read-only.

## Não versionar

- tokens;
- hashes de tokens;
- senhas;
- secrets;
- chaves privadas;
- `.env` real;
- dumps sem sanitização.

## Pendências

- imutabilidade de `installation_id`;
- autenticação de usuário adicional para o dashboard;
- testes automatizados de autorização;
- política formal de retenção/auditoria.
