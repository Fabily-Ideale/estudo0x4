Configuração do agente
===
Aqui apenas registro as configurações que uso em meu agente - tanto para minha utilização para uso de quem quiser.

Cada IDE/Agente tem uma forma de configurar isso, caso não saiba usar na sua... "Vá estudar".

Estrutura
---
| Pasta | Conteúdo |
|---|---|
| `claude/` | Configuração atual (Claude Code) |
| `gemini/` | Configuração legada (Antigravity / Gemini) |

Claude Code
---
| Arquivo | Destino | Função |
|---|---|---|
| `claude/CLAUDE.md` | `~/.claude/CLAUDE.md` | Regras globais (idioma, padrões de código, segurança, circuit breaker) |
| `claude/skills/missao/` | `~/.claude/skills/missao/` | Fluxo de 4 fases sob demanda: `/missao <descrição>` |
| `claude/agents/qa-validator.md` | `~/.claude/agents/` | Subagente da fase de validação (build, testes, segredos expostos, SQL) |
| `claude/mcp-servers.json` | via `claude mcp` | Servidores MCP opcionais |

### Instalação (Git Bash)
```bash
mkdir -p ~/.claude/agents ~/.claude/skills && cp claude/CLAUDE.md ~/.claude/ && cp claude/agents/*.md ~/.claude/agents/ && cp -r claude/skills/* ~/.claude/skills/
```

### Skills da Anthropic
Não são copiadas para este repositório; instale pelo marketplace oficial (atualiza automaticamente):
```
/plugin marketplace add anthropics/skills

/plugin install example-skills@anthropic-agent-skills
```

Licenças
---
O `LICENSE` (CC0) cobre apenas o conteúdo autoral deste repositório. As skills em `gemini/skills/` foram obtidas da Anthropic e mantêm suas próprias licenças (`LICENSE.txt` em cada pasta). As skills `docx`, `pdf`, `pptx` e `xlsx` foram removidas por terem licença proprietária que não permite redistribuição.
