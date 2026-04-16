# TS 1.5 — Persistência em background

## Objetivo

Salvar o resultado da equação no histórico do usuário sem bloquear a resposta ao cliente.

## Tarefas

- [ ] Verificar se o request contém JWT válido após resolver a equação
- [ ] Se autenticado: salvar em `EquationHistory` com os campos `username`, `equation`, `result`, `steps[]`, `createdAt`
- [ ] Se não autenticado: retornar resultado normalmente, sem persistir e sem retornar erro
- [ ] A persistência não deve bloquear a resposta (fire-and-forget assíncrono)
- [ ] Em caso de falha na persistência: apenas registrar log interno, não propagar ao cliente
- [ ] Usar driver `motor` para escrita assíncrona

**Labels:** `backend` `mongodb` `auth`
**Story Points:** 2
