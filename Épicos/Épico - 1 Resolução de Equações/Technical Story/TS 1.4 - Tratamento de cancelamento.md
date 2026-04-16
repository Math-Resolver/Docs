# TS 1.4 — Tratamento de cancelamento

## Objetivo

Interromper o processamento da equação quando o cliente desconectar antes da resposta.

## Tarefas

- [ ] Checar `request.is_disconnected()` durante o processamento
- [ ] Usar `asyncio.CancelledError` para interromper a execução quando aplicável
- [ ] Garantir que o cancelamento não cause efeitos colaterais (ex: persistência parcial)

**Labels:** `backend` `solver`
**Story Points:** 1
