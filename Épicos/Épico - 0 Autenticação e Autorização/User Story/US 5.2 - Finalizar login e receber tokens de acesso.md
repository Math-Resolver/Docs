# ÉPICO — Autenticação: Login (WebAuthn)

---

## US 5.2 — Finalizar login e receber tokens de acesso

### História de Usuário

**Como** usuário já cadastrado,
**Quero** enviar minha credencial biométrica para concluir o login,
**Para que** eu receba um `access_token` e um `refresh_token` para acessar o app.

---

### Critérios de Aceitação

- [ ] O endpoint `POST /v1/auth/login/finish` deve aceitar: `{ "credential": "hashASAHASD..." }`
- [ ] Recuperar o challenge salvo correspondente à credencial
- [ ] Buscar a `publicKey` do usuário na collection `Users`
- [ ] Validar a credencial usando a `publicKey`
- [ ] Se inválida, retornar `401 Unauthorized`
- [ ] Se válida: gerar `access_token` (JWT de curta duração) e `refresh_token`
- [ ] Persistir o `refresh_token` na collection `RefreshTokens` com `isRevoked: false` e `expirationDate` de 7 dias
- [ ] O hash do `refresh_token` deve ser salvo (não o token em texto plano)
- [ ] Invalidar o challenge após uso
- [ ] A resposta deve conter: `{ "access_token": "...", "refresh_token": "..." }`

---

### Tasks

- [ ] Criar router `POST /v1/auth/login/finish` no FastAPI
- [ ] Criar schema Pydantic para o body: `credential: str`
- [ ] Criar schema Pydantic para a resposta: `access_token: str`, `refresh_token: str`
- [ ] Implementar service `get_challenge_by_credential()` (reutilizar do cadastro)
- [ ] Implementar service `get_public_key_by_user()`: busca `publicKey` na collection `Users`
- [ ] Implementar service `validate_credential_with_public_key()`: valida assinatura
- [ ] Implementar service `generate_tokens()`: gera JWT (access) e refresh token
- [ ] Implementar service `persist_refresh_token()`: salva hash do token em `RefreshTokens`
- [ ] Implementar invalidação do challenge após uso
- [ ] Criar índice TTL na collection `RefreshTokens` pelo campo `expirationDate`
- [ ] Mapear credencial inválida para HTTP 401
- [ ] Escrever teste: credencial válida -> 200 + access_token + refresh_token persistido
- [ ] Escrever teste: credencial inválida -> 401
- [ ] Escrever teste: challenge expirado -> 400
- [ ] Escrever teste: refresh_token salvo com isRevoked: false

---

**Labels:** `feature` `backend` `auth` `webauthn` `jwt`
**Story Points:** 5
