# TS 1.6 — Idempotência da escrita no histórico

## Objetivo

Garantir que retentativas de escrita não gerem duplicatas na collection `EquationHistory`.

## Tarefas

- [ ] Implementar `upsert` com chave composta `(username, equation, createdAt)` em lugar de insert simples
- [ ] Criar índice único no MongoDB: `{ username: 1, equation: 1, createdAt: 1 }`

**Labels:** `backend` `mongodb`
**Story Points:** 1
