# OpenCode Dev

Repositório central de **agents** e **skills** customizados para o [opencode](https://opencode.ai).

## O que é?

Este projeto fornece um conjunto de agents especializados e skills que podem ser integrados a qualquer projeto para melhorar o fluxo de desenvolvimento com o opencode.

---

## Estrutura

```
opencode-dev/
├── AGENTS.md              # Documentação principal (agents e skills)
├── opencode.json          # Configuração do opencode
└── .opencode/
    ├── agent/             # Definições dos agents
    │   ├── compose.md     # @compose - Coordenador central
    │   ├── frontend.md    # @frontend - Interface web/mobile
    │   ├── backend.md     # @backend - APIs e backend
    │   ├── database.md    # @database - Bancos de dados SQL
    │   └── code-reviewer.md
    └── skills/            # Skills especializadas
        ├── fix-bug/
        ├── react-best-practices/
        ├── react-native-skills/
        ├── react-view-transitions/
        ├── web-design-guidelines/
        └── writing-guidelines/
```

---

## Como Usar

### Opção 1: Copiar `.opencode/` (Recomendado)

```bash
cp -r .opencode/ /caminho/do/seu-projeto/opencode/
```

### Opção 2: Apontar no `opencode.json`

```json
{
  "skills": {
    "paths": ["/caminho/para/opencode-dev/.opencode/skills"]
  }
}
```

---

## Agents

| Agent | Modo | Descrição |
|-------|------|----------|
| `@compose` | Primary | Coordenador central — ponto de entrada para novos recursos/correções |
| `@frontend` | Subagent | Interface web/mobile — React, React Native, View Transitions |
| `@backend` | Subagent | APIs e serviços backend |
| `@database` | Subagent | Banco de dados SQL |

### Exemplos de Uso

```bash
# Iniciar novo recurso via @compose
@compose: Crie o recurso X que faz Y

# Delegar para agente especializado
@frontend: Implemente o componente de login
@backend: Crie a API de autenticação
@database: Crie as tabelas para usuários
```

---

## Skills

Skills são carregadas automaticamente quando o modelo detecta relevância pela descrição.

| Skill | Descrição |
|-------|----------|
| `fix-bug` | Corrigir bugs e investigar erros |
| `web-design-guidelines` | Web Interface Guidelines (UX/accessibility) |
| `writing-guidelines` | Guidelines para documentação |
| `react-view-transitions` | View Transitions API |
| `react-best-practices` | 70+ regras de performance React/Next.js |
| `react-native-skills` | 35+ regras React Native/Expo |

---

## Fluxo de Trabalho

1. **@compose** recebe pedido → analisa → cria especificação em `docs/feature/`
2. **@compose** delega para `@frontend`, `@backend`, `@database`
3. Cada agent implementa e reporta para @compose
4. **@compose** cria documento pós-implementação

---

## Regras

- Skills são ativadas automaticamente pela `description`
- Mantenha `SKILL.md` com menos de 500 linhas
- Scripts: stderr para logs, stdout para JSON estruturado
- Reinicie o opencode após mudanças de configuração
