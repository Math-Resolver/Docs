# TS 2.1 — Endpoint protegido de histórico

## Objetivo

Implementar o endpoint de consulta de histórico exigindo JWT válido.

## Tarefas

- [ ] Criar router `GET /v1/equation/history`
- [ ] Exigir header `Authorization: Bearer <token>`
- [ ] Retornar `401 Unauthorized` para token ausente ou inválido
- [ ] Criar schema Pydantic para a resposta: lista de `{ equation, result, steps[] }`

**Labels:** `backend` `auth` `mongodb`
**Story Points:** 2
