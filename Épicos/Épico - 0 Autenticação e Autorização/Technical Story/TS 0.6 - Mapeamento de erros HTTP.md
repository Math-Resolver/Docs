# TS 0.6 — Mapeamento de erros HTTP

## Objetivo

Garantir que todos os casos de erro retornem o status HTTP correto e com mensagem descritiva.

## Tarefas

- [ ] `409 Conflict` — conflito de `displayName` já cadastrado
- [ ] `404 Not Found` — usuário não encontrado ou sem credencial registrada no login
- [ ] `400 Bad Request` — challenge expirado, não encontrado ou inválido
- [ ] `401 Unauthorized` — credencial inválida, token expirado, token revogado ou token inexistente
- [ ] Garantir que nenhum erro exponha stack trace ou dados internos na resposta
- [ ] Padronizar formato de erro: `{ "detail": "mensagem" }`

**Labels:** `backend` `auth` `security`
**Story Points:** 1
