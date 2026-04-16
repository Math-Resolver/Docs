# TS 2.5 — Cancelamento de consulta

## Objetivo

Abandonar a consulta ao banco quando o cliente desconectar antes de receber a resposta.

## Tarefas

- [ ] Verificar `request.is_disconnected()` antes de iniciar a query
- [ ] Verificar `request.is_disconnected()` após a query retornar (antes de serializar)
- [ ] Não retornar resposta nem consumir recursos adicionais em caso de desconexão

**Labels:** `backend` `mongodb`
**Story Points:** 1
