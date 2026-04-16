# TS 1.2 — Detector de tipo de equação

## Objetivo

Criar um módulo isolado que classifica automaticamente o tipo da equação antes de chamar qualquer solver.

## Tarefas

- [ ] Criar módulo `equation_type_detector.py`
- [ ] Classificar corretamente: **linear**, **quadrática** e **sistema de equações**
- [ ] Usar `sympy` para análise do grau do polinômio
- [ ] A classificação deve ocorrer após o parsing e antes de despachar ao solver
- [ ] Se tipo não reconhecido: lançar exceção interna que resulte em `422 Unprocessable Entity`
- [ ] Garantir que o módulo não tenha acoplamento direto ao endpoint

**Labels:** `backend` `solver` `refactor`
**Story Points:** 2
