# TS 0.3 — Gestão de challenge

## Objetivo

Implementar criação, persistência e invalidação segura de challenges WebAuthn.

## Tarefas

- [ ] Implementar service `generate_challenge()`: gera hash único e salva em `Challenges` com TTL de 5 min
- [ ] Configurar TTL index no MongoDB na collection `Challenges`: `expirationDate` com `expireAfterSeconds=0`
- [ ] Implementar service `get_challenge_by_credential()`: busca challenge ativo
- [ ] Implementar invalidação imediata após uso (delete do documento)
- [ ] Garantir idempotência por `deviceFingerprint` na janela de 5 min: mesma combinação retorna o mesmo challenge sem criar duplicata

**Labels:** `backend` `auth` `webauthn` `mongodb`
**Story Points:** 2
