# 📌 ÉPICO — Autenticação: Cadastro (WebAuthn)

---

## 🎫 US 4.1 — Iniciar cadastro e receber challenge

### História de Usuário

**Como** novo usuário do app,  
**Quero** iniciar meu cadastro enviando meu e-mail e a identificação do meu dispositivo,  
**Para que** eu receba um challenge para completar o registro com biometria.

---

### Critérios de Aceitação

- [ ] O endpoint `POST /v1/auth/register` deve aceitar:
      `{ "displayName": "user@email.com", "deviceFingerprint": "iPhone15,5/uuid" }`
- [ ] Criar o usuário na collection `Users` com `credentialId: null` e `publicKey: null`
- [ ] Gerar um challenge único, salvá-lo na collection `Challenges` com `expirationDate` de **5 minutos**
- [ ] O challenge **nunca deve ser reutilizado** — após uso ou expiração, deve ser invalidado
- [ ] A resposta deve conter: `challenge`, `relyingParty`, `user.id` e `user.username`
- [ ] Se o `displayName` já estiver cadastrado, retornar `409 Conflict`
- [ ] O endpoint deve ser **idempotente por deviceFingerprint**: mesma combinação dentro da janela de 5 min retorna o mesmo challenge sem criar duplicata

---

### Tasks

- [ ] Criar router `POST /v1/auth/register` no FastAPI
- [ ] Criar schema Pydantic para o body: `displayName: str`, `deviceFingerprint: str`
- [ ] Criar schema Pydantic para a resposta: `challenge`, `relyingParty`, `user`
- [ ] Implementar service `create_user()`: cria documento na collection `Users`
- [ ] Implementar service `generate_challenge()`: gera hash único e salva em `Challenges` com TTL de 5 min
- [ ] Configurar TTL index no MongoDB na collection `Challenges`: `expirationDate` com expireAfterSeconds=0
- [ ] Garantir unicidade de `displayName` com índice único na collection `Users`
- [ ] Mapear conflito de `displayName` para HTTP 409
- [ ] Escrever teste: novo usuário → 200 + challenge gerado
- [ ] Escrever teste: displayName duplicado → 409
- [ ] Escrever teste: mesma requisição dentro de 5 min → retorna mesmo challenge (idempotência)

---

**Labels:** `feature` `backend` `auth` `webauthn`  
**Story Points:** 5