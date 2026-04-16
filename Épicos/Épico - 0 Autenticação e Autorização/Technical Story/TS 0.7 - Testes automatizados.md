# TS 0.7 — Testes unitários

## Objetivo

Garantir cobertura dos fluxos de cadastro, login e refresh com testes automatizados.

## Tarefas

### Cadastro
- [ ] Novo usuário → `200` + challenge gerado
- [ ] `displayName` duplicado → `409`
- [ ] Mesma requisição dentro de 5 min → retorna mesmo challenge (idempotência)
- [ ] Credencial válida → usuário atualizado + challenge deletado
- [ ] Challenge expirado → `400`
- [ ] Credencial inválida → `401`

### Login
- [ ] E-mail válido com credencial cadastrada → `200` + challenge gerado
- [ ] E-mail não cadastrado → `404`
- [ ] Credencial válida → `200` + access_token + refresh_token persistido com `isRevoked: false`
- [ ] Credencial inválida → `401`
- [ ] Challenge expirado → `400`

### Refresh token
- [ ] Token válido → `200` + novo par de tokens + token antigo revogado
- [ ] Token expirado → `401`
- [ ] Token revogado → `401`
- [ ] Token inexistente → `401`
- [ ] Atomicidade: falha na inserção do novo token não deve revogar o antigo

**Labels:** `backend` `auth` `testes`
**Story Points:** 3
