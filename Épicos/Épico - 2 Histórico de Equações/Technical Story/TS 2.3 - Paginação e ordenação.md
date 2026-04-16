# TS 2.3 — Paginação e ordenação

## Objetivo

Implementar paginação configurável e ordenação decrescente por data de criação.

## Tarefas

- [ ] Aceitar query params `page` (default: `1`) e `limit` (default: `3`)
- [ ] Calcular `skip = (page - 1) * limit`
- [ ] Aplicar `.sort({ createdAt: -1 }).skip(skip).limit(limit)` na query
- [ ] Validar que `page` e `limit` são inteiros positivos

**Labels:** `backend` `mongodb`
**Story Points:** 1
