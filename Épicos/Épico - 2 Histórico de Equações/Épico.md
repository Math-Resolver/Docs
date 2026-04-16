# Épico 2 — Histórico de Equações

## Objetivo

Disponibilizar para o usuário autenticado uma consulta paginada e segura de todas as equações que ele já resolveu, com dados completos de resultado e passos.

## Escopo

- Endpoint protegido por JWT que retorna o histórico do usuário
- Paginação configurável com ordenação por data decrescente
- Isolamento total de dados entre usuários
- Suporte a cancelamento de consulta em caso de desconexão do cliente

## Histórias de Usuário

| ID   | Título |
|------|--------|
| US 2.1 | Buscar histórico do usuário autenticado |

## Tarefas Técnicas

| ID     | Título |
|--------|--------|
| TS 2.1 | Endpoint protegido de histórico |
| TS 2.2 | Isolamento por usuário |
| TS 2.3 | Paginação e ordenação |
| TS 2.4 | Contrato e metadados de resposta |
| TS 2.5 | Cancelamento de consulta |
| TS 2.6 | Testes |

## Dependências

- Collection `EquationHistory` populada pelo Épico 1
- Módulo JWT do Épico 0 para extração do `username`
- Header `X-Total-Count` consumido pelo cliente Flutter

**Labels:** `backend` `mongodb` `auth`
