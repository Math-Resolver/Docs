# TS 1.1 — API de resolução de equações

## Objetivo

Implementar o endpoint principal de resolução de equações.

## Tarefas

- [ ] Criar router `POST /v1/equation/solve`
  - Aceitar `{ "equation": "2*x + 5 = 15", "showSteps": true }`
  - Retornar `{ "result": "...", "steps": [] }`
  - Se `showSteps: false`, retornar `steps` como array vazio (não omitir a chave)
- [ ] Criar schema Pydantic para body e resposta
- [ ] Retornar `400 Bad Request` para equação inválida, com mensagem descritiva
- [ ] Retornar `422 Unprocessable Entity` para tipo de equação não suportado
- [ ] Garantir idempotência: mesma equação deve retornar sempre o mesmo resultado

**Labels:** `backend` `solver`
**Story Points:** 2
