# TS 0.2 — Endpoints de login WebAuthn

## Objetivo

Implementar os dois endpoints do fluxo de login via WebAuthn no FastAPI.

## Tarefas

- [ ] Criar router `POST /v1/auth/login`
  - Aceitar `{ "email": "user@email.com" }`
  - Retornar `{ challenge, relyingParty, user }`
  - Mapear usuário não encontrado ou sem credencial para `404`
- [ ] Criar router `POST /v1/auth/login/finish`
  - Aceitar `{ "credential": "..." }`
  - Retornar `{ access_token, refresh_token }`
  - Mapear credencial inválida para `401`, challenge expirado para `400`
- [ ] Criar schemas Pydantic para body e resposta de ambos endpoints
- [ ] Validar credencial contra `publicKey` armazenada na collection `Users`

**Labels:** `backend` `auth` `webauthn`
**Story Points:** 2
