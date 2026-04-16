# TS 3.3 — Segurança e cancelamento

## Objetivo

Garantir isolamento por usuário e suporte a cancelamento de consulta.

## Tarefas

- [ ] Filtrar a query sempre pelo `username` extraído do JWT
- [ ] Verificar `request.is_disconnected()` antes e após a query ao banco
- [ ] Abandonar a consulta sem retornar resposta em caso de desconexão

**Labels:** `backend` `security`
**Story Points:** 1
