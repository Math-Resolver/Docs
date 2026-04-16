# TS 0.1 — Endpoints de cadastro WebAuthn

## Objetivo

Implementar os dois endpoints do fluxo de cadastro via WebAuthn no FastAPI.

## Tarefas

- [ ] Criar router `POST /v1/auth/register`
  - Aceitar `{ "displayName": "user@email.com", "deviceFingerprint": "..." }`
  - Retornar `{ challenge, relyingParty, user }`
- [ ] Criar router `POST /v1/auth/register/finish`
  - Aceitar `{ "credential": "..." }`
  - Retornar `200 OK` com confirmação
  - Mapear credencial inválida para `401`, challenge expirado para `400`
- [ ] Criar schemas Pydantic para body e resposta de ambos endpoints
- [ ] Registrar routers no app FastAPI

**Labels:** `backend` `auth` `webauthn`
**Story Points:** 2
