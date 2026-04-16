# ÉPICO — Autenticação: Login (WebAuthn)

---

## US 5.1 — Iniciar login e receber challenge

### História de Usuário

**Como** usuário já cadastrado,
**Quero** informar meu e-mail para iniciar o login,
**Para que** eu receba um challenge para autenticar com a biometria do meu dispositivo.

---

### Critérios de Aceitação

- [ ] O endpoint `POST /v1/auth/login` deve aceitar: `{ "email": "user@email.com" }`
- [ ] Buscar as credenciais do usuário na collection `Users`
- [ ] Se o usuário não existir ou não tiver `credentialId`, retornar `404 Not Found`
- [ ] Gerar um novo challenge e persistir na collection `Challenges` com `expirationDate` de 5 minutos
- [ ] O challenge **nunca deve ser reutilizado**
- [ ] A resposta deve conter: `challenge`, `relyingParty`, `user.id` e `user.username`
- [ ] O endpoint deve aparecer no menu do app como opção de login (anotação de UX do diagrama)

---

### Tasks

- [ ] Criar router `POST /v1/auth/login` no FastAPI
- [ ] Criar schema Pydantic para o body: `email: str`
- [ ] Criar schema Pydantic para a resposta: `challenge`, `relyingParty`, `user`
- [ ] Implementar service `get_user_credentials()`: busca usuário e valida que tem credencial registrada
- [ ] Reutilizar service `generate_challenge()` do fluxo de cadastro
- [ ] Mapear usuário não encontrado ou sem credencial para HTTP 404
- [ ] Escrever teste: e-mail válido com credencial cadastrada -> 200 + challenge gerado
- [ ] Escrever teste: e-mail não cadastrado -> 404
- [ ] Escrever teste: usuário sem credencial registrada -> 404

---

**Labels:** `feature` `backend` `auth` `webauthn`
**Story Points:** 3
