# TS 0.5 — Rotação de refresh token (token rotation)

## Objetivo

Implementar o endpoint de renovação de sessão com revogação e reinserção atômica do refresh token.

## Tarefas

- [ ] Criar router `POST /v1/auth/refresh-token`
  - Aceitar `{ "token": "..." }`
  - Retornar `{ access_token, refresh_token }`
- [ ] Criar schema Pydantic para body e resposta
- [ ] Implementar service `find_refresh_token()`: busca na collection `RefreshTokens`
- [ ] Implementar validações:
  - [ ] Token inexistente → `401`
  - [ ] `expirationDate` expirado → `401`
  - [ ] `isRevoked: true` → `401`
- [ ] Implementar service `rotate_refresh_token()`:
  - [ ] Marcar token atual como `isRevoked: true`
  - [ ] Inserir novo documento com `isRevoked: false` e nova `expirationDate`
  - [ ] Usar sessão/transação MongoDB para garantir atomicidade
- [ ] Reutilizar service `generate_tokens()` do fluxo de login

**Labels:** `backend` `auth` `jwt` `security` `mongodb`
**Story Points:** 3
