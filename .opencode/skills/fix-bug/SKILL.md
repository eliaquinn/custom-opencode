---
name: fix-bug
description: >
  Use quando o usuário relatar erro em runtime, crash, teste falhando, ou pedir
  para "corrigir isso", "investigar" ou abrir um PR de bugfix. Não use para
  code review ou features novas. Gatilhos: "bug", "crash", "erro", "não funciona",
  "está quebrando", "500", "failed".
---

# Corrigir Bug

Procedimento de diagnóstico e correção de bugs.

## How It Works

1. Reproduza o erro e colete stack trace/estado.
2. Isole a causa raiz (git bisect, testes, bissecção manual).
3. Avalie o menor patch que corrige sem quebrar o comportamento atual.
4. Execute a suíte de testes e linter antes de finalizar.

## Present Results to User

Apresente:
- Causa raiz identificada
- Patch aplicado (diff resumido)
- Comando para verificar a correção
