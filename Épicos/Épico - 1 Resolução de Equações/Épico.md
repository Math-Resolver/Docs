# Épico 1 — Resolução de Equações

## Objetivo

Implementar o núcleo funcional do app Killmath: receber uma equação matemática, identificar seu tipo, resolvê-la com passos detalhados e (quando autenticado) salvar o resultado no histórico do usuário.

## Escopo

- API de resolução com suporte a equações lineares, quadráticas e sistemas
- Detecção automática do tipo da equação e roteamento ao solver correto
- Retorno de passos de resolução quando solicitado
- Persistência assíncrona em background para usuários autenticados
- Suporte a cancelamento de requisição

## Histórias de Usuário

| ID   | Título |
|------|--------|
| US 1.1 | Resolver equação via API e retornar resultado com passos |
| US 1.2 | Detectar e rotear tipo de equação automaticamente |
| US 1.3 | Persistir resultado para usuário autenticado |

## Tarefas Técnicas

| ID     | Título |
|--------|--------|
| TS 1.1 | API de resolução de equações |
| TS 1.2 | Detector de tipo de equação |
| TS 1.3 | Implementação dos solvers |
| TS 1.4 | Tratamento de cancelamento |
| TS 1.5 | Persistência em background |
| TS 1.6 | Idempotência da escrita |
| TS 1.7 | Testes |

## Dependências

- Biblioteca `sympy` para análise e resolução de equações
- Driver `motor` para escrita assíncrona no MongoDB
- Módulo JWT do Épico 0 para identificar usuário autenticado

**Labels:** `solver` `backend` `mongodb`
