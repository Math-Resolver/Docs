# ÉPICO — Autenticação: Cadastro (WebAuthn)

---

## US 4.2 — Finalizar cadastro com credencial biométrica

### História de Usuário

**Como** novo usuário do app,  
**Quero** enviar minha credencial gerada pela biometria do dispositivo,  
**Para que** meu cadastro seja concluído e minha chave pública fique vinculada à minha conta.

---

### Critérios de Aceitação

- [ ] O endpoint `POST /v1/auth/register/finish` deve aceitar: `{ "credential": "hashASAHASD..." }`
- [ ] Recuperar o challenge salvo correspondente à credencial recebida
- [ ] Se o challenge não existir ou estiver expirado, retornar `400 Bad Request`
- [ ] Validar a resposta da credencial contra o challenge
- [ ] Se válida: atualizar o usuário na collection `Users` com `credentialId` e `publicKey`
- [ ] Após uso, o challenge deve ser **imediatamente invalidado** (deletado ou marcado como usado)
- [ ] Retornar `200 OK` com confirmação após atualização bem-sucedida
- [ ] Se a credencial for inválida, retornar `401 Unauthorized`

---

### Tasks

- [ ] Criar router `POST /v1/auth/register/finish` no FastAPI
- [ ] Criar schema Pydantic para o body: `credential: str`
- [ ] Implementar service `get_challenge_by_credential()`: busca challenge ativo na collection `Challenges`
- [ ] Implementar service `validate_credential()`: valida a resposta contra o challenge
- [ ] Implementar service `update_user_credential()`: salva `credentialId` e `publicKey` no usuário
- [ ] Implementar invalidação imediata do challenge após uso (delete do documento)
- [ ] Mapear credencial inválida para HTTP 401
- [ ] Mapear challenge expirado/não encontrado para HTTP 400
- [ ] Escrever teste: credencial válida → usuário atualizado + challenge deletado
- [ ] Escrever teste: challenge expirado → 400
- [ ] Escrever teste: credencial inválida → 401

---

**Labels:** `feature` `backend` `auth` `webauthn`  
**Story Points:** 3
