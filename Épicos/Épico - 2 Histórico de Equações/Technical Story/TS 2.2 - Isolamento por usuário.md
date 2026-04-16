# TS 2.2 — Isolamento por usuário

## Objetivo

Garantir que cada usuário veja apenas seus próprios registros.

## Tarefas

- [ ] Extrair `username` do JWT na requisição
- [ ] Filtrar a query em `EquationHistory` sempre com `{ username: <username_do_jwt> }`
- [ ] Garantir (por teste) que nenhum registro de outro usuário apareça na resposta

**Labels:** `backend` `auth` `security`
**Story Points:** 1
