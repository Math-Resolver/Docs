# Épico 0 — Autenticação e Autorização

## Objetivo

Implementar o ciclo completo de identidade do usuário no app Killmath, usando **WebAuthn** (biometria do dispositivo) como método de autenticação sem senha, combinado com **JWT** (access token de curta duração + refresh token rotativo) para controle de sessão.

## Escopo

- Cadastro em dois passos: solicitar challenge → enviar credencial biométrica
- Login em dois passos: solicitar challenge → enviar credencial → receber tokens
- Renovação segura de sessão via token rotation, com revogação atômica do token anterior

## Histórias de Usuário

| ID   | Título |
|------|--------|
| US 4.1 | Iniciar cadastro e receber challenge |
| US 4.2 | Finalizar cadastro com credencial biométrica |
| US 5.1 | Iniciar login e receber challenge |
| US 5.2 | Finalizar login e receber tokens de acesso |
| US 6.1 | Renovar access token via refresh token |

## Tarefas Técnicas

| ID     | Título |
|--------|--------|
| TS 0.1 | Endpoints de cadastro WebAuthn |
| TS 0.2 | Endpoints de login WebAuthn |
| TS 0.3 | Gestão de challenge |
| TS 0.4 | Persistência e segurança de usuário/tokens |
| TS 0.5 | Rotação de refresh token |
| TS 0.6 | Mapeamento de erros HTTP |
| TS 0.7 | Testes automatizados |

## Dependências

- MongoDB com suporte a transações (replica set)
- Biblioteca WebAuthn para validação de credenciais
- Módulo JWT compartilhado com os demais épicos

**Labels:** `auth` `backend` `webauthn` `jwt` `security`
