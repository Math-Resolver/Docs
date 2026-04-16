# TS 1.7 — Testes

## Objetivo

Garantir cobertura dos fluxos de resolução, detecção de tipo e persistência.

## Tarefas

### API de resolução
- [ ] Equação linear válida com `showSteps: true` → `200` + `result` + `steps` populado
- [ ] Equação válida com `showSteps: false` → `200` + `steps: []`
- [ ] Equação inválida → `400` com mensagem descritiva
- [ ] Tipo não suportado → `422`

### Detector de tipo
- [ ] Equação linear → classificada como linear
- [ ] Equação quadrática → classificada como quadrática
- [ ] Sistema → classificado como sistema
- [ ] Entrada não reconhecida → exceção mapeada para `422`

### Persistência
- [ ] Usuário autenticado → resultado salvo em `EquationHistory`
- [ ] Usuário não autenticado → nenhum documento criado, resposta `200` normal
- [ ] Falha na escrita → resposta `200` sem propagar erro
- [ ] Retentativa → sem duplicata (idempotência via `upsert`)

**Labels:** `backend` `testes`
**Story Points:** 3
