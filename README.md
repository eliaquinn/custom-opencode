# OpenCode Custom Agents & Skills

Repositório central de **agents** e **skills** customizados para o [opencode](https://opencode.ai).

## O que é?

Este projeto fornece um conjunto de agents especializados e skills que podem ser integrados a qualquer projeto para melhorar o fluxo de desenvolvimento com o opencode.

---

## Estrutura

```
opencode-dev/
├── README.md              # Este arquivo
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
        ├── react-composition-patterns/
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

## Agentes

| Agent | Modo | Descrição |
|-------|------|----------|
| `@compose` | Subagent | **Ponto de entrada** — Coordenador central para novos recursos/correções |
| `@frontend` | Subagent | Interface web/mobile — React, React Native, View Transitions |
| `@backend` | Subagent | APIs e serviços backend |
| `@database` | Subagent | Banco de dados SQL |

### Modo de Uso

1. **Inicie a conversa com @compose** — Este é o ponto de entrada para qualquer nova tarefa:

```bash
@compose: Crie o recurso X que faz Y
```

2. **O @compose analisa e delega** para os agentes especializados conforme necessário

3. **Agents disponíveis para delegação:**

```bash
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
| `react-composition-patterns` | Padrões de composição React (compound components, context, etc) |

---

## Fluxo de Trabalho

1. **@compose** recebe pedido → analisa → cria especificação em `docs/feature/`
2. **@compose** delega para `@frontend`, `@backend`, `@database`
3. Cada agent implementa e reporta para @compose
4. **@compose** cria documento pós-implementação

---

## Estrutura de Documentação (docs/)

O `@compose` mantém uma estrutura organizada:

```
docs/
├── feature/          # Especificações de novos recursos
│   └── {nome}-{data}.md
├── fix/             # Documentação de correções
│   └── {problema}-{data}.md
└── memory/          # Histórico de decisões
    └── {contexto}-{data}.md
```

---

## Regras

- **@compose é o ponto de entrada** — Sempre inicie com ele para novas tarefas
- Skills são ativadas automaticamente pela `description`
- Mantenha `SKILL.md` com menos de 500 linhas
- Reinicie o opencode após mudanças de configuração
