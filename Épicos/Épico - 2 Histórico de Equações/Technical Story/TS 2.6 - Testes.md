# TS 2.6 — Testes

## Objetivo

Garantir cobertura completa do endpoint de histórico.

## Tarefas

- [ ] Usuário autenticado → retorna lista paginada com `200`
- [ ] Token ausente → `401`
- [ ] Token inválido → `401`
- [ ] Paginação: `page=2&limit=2` retorna registros corretos com `skip` aplicado
- [ ] Ordenação: registros retornam por `createdAt` DESC
- [ ] Isolamento: usuário A não vê registros do usuário B
- [ ] `X-Total-Count` reflete total real de registros do usuário

**Labels:** `backend` `testes`
**Story Points:** 2
