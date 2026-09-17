# Agentes e Skills

Este repositório centraliza skills e agents customizados para o opencode.

---

## Como Usar em Qualquer Projeto

### Opção 1: Copiar `.opencode/` (Recomendado)

```bash
# No seu projeto
cp -r /caminho/para/opencode-dev/.opencode/ ./opencode/
```

Isso ativa tudo automaticamente — skills e agents estão disponíveis.

### Opção 2: Apontar `skills.paths`

Adicione ao `opencode.json` do seu projeto:

```json
{
  "skills": {
    "paths": ["/caminho/para/opencode-dev/.opencode/skills"]
  }
}
```

---

## Agents Disponíveis

| Agent | Modo | Descrição |
|-------|------|----------|
| `@compose` | Primary | Coordenador central — ponto de entrada para novos recursos/correções |
| `@frontend` | Subagent | Interface web/mobile — React, React Native, View Transitions |
| `@backend` | Subagent | APIs e serviços backend |
| `@database` | Subagent | Banco de dados SQL |

### Usando os Agents

**Iniciar um novo recurso:**
```
@compose: Crie o recurso X que faz Y
```

**Delegar para agente especializado:**
```
@frontend: Implemente o componente de login
@backend: Crie a API de autenticação
@database: Crie as tabelas para usuários
```

---

## Skills Disponíveis

Skills são carregadas automaticamente quando o modelo detecta relevância pela `description`.

| Skill | Descrição |
|-------|----------|
| `fix-bug` | Corrigir bugs e investigar erros |
| `web-design-guidelines` | Web Interface Guidelines (UX/accessibility) |
| `writing-guidelines` | Guidelines para documentação |
| `react-view-transitions` | View Transitions API |
| `react-best-practices` | 70+ regras de performance React/Next.js |
| `react-native-skills` | 35+ regras React Native/Expo |

---

## Estrutura de Documentação (docs/)

O `@compose` mantém uma estrutura organizada:

```
docs/
├── feature/          # Especificações de novos recursos
├── fix/             # Documentação de correções
└── memory/          # Histórico de decisões
```

### Fluxo Típico

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
