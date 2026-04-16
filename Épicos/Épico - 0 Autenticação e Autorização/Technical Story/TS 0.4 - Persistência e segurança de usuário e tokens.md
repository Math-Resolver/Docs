# TS 0.4 — Persistência e segurança de usuário/tokens

## Objetivo

Garantir que dados sensíveis de usuários e tokens sejam armazenados com segurança no MongoDB.

## Tarefas

- [ ] Criar collection `Users` com índice único em `displayName`
- [ ] Implementar service `create_user()`: cria documento com `credentialId: null` e `publicKey: null`
- [ ] Implementar service `update_user_credential()`: salva `credentialId` e `publicKey` após cadastro
- [ ] Criar collection `RefreshTokens`: armazenar apenas o **hash** do token (nunca texto plano)
- [ ] Configurar TTL index em `RefreshTokens.expirationDate` para limpeza automática após 7 dias
- [ ] Implementar service `persist_refresh_token()`: salva hash com `isRevoked: false` e `expirationDate`

**Labels:** `backend` `auth` `mongodb` `security`
**Story Points:** 2
