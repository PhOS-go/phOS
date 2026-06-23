---
name: mapear-rotinas
description: >
  Mapeia tarefas repetitivas do dia a dia e gera skills personalizadas pra automatizá-las. Faz
  uma entrevista curta sobre o que o usuário repete toda semana, propõe comandos concretos e cria
  os aprovados em .claude/skills/. Use quando o usuário pedir "/mapear-rotinas", "criar skills",
  "automatizar minhas tarefas" ou "o que dá pra automatizar".
---

# /mapear-rotinas: Transformar rotina repetida em comando

Skill de descoberta + criação. O objetivo é transformar o que o usuário repete em automação ativa.

## Workflow

### Passo 1: Entrevista de descoberta (3 perguntas)

1. "Quais 3 tarefas você repete toda semana e queria não ter que pensar mais? (ex: 'fazer carrossel', 'mandar relatório pro cliente', 'escrever briefing')"
2. "Pra cada uma, qual o input típico? (ex: 'um link de notícia', 'uma planilha', 'um nome de cliente')"
3. "E o output que você espera? (ex: '5 slides em PNG', 'um e-mail pronto', 'um PDF resumindo')"

### Passo 2: Conferir o catálogo

Ler `templates/skills/catalogo.md` pra ver se alguma tarefa já é coberta por skill nativa do
Claude Code ou já existente no phOS. Se sim, sugerir a existente em vez de criar nova:
> "A tarefa X já é resolvida pela skill `/<nome>`. Quer usar ela em vez de criar uma nova?"

### Passo 3: Propor os comandos

Pra cada tarefa SEM cobertura, propor:

```
### /<nome-da-skill>
**O que faz:** [uma frase]
**Input:** [o que recebe]
**Output:** [o que entrega]
**Depende de:** [arquivos de memoria/, marca/, ou ferramentas externas]
```

Mostrar todas juntas e perguntar:
> "Quais desses você quer que eu crie agora? (todos, alguns, nenhum, também pode pedir ajustes)"

### Passo 4: Criar os aprovados

Pra cada skill aprovada:
1. Criar pasta `.claude/skills/<nome>/`
2. Criar `SKILL.md` com:
   - Frontmatter: `name` (igual ao da pasta) e `description` (diz *quando* invocar)
   - Workflow em fases ou passos
   - Dependências (arquivos de contexto, ferramentas)
   - Regras claras (o que sempre / nunca fazer)
3. Se precisar de moldes ou exemplos, criar dentro da pasta da skill
4. Calibrar tom e regras por `memoria/voz.md` e `memoria/perfil.md`

### Passo 5: Resumo

```
Criei [N] comandos:
✓ /<nome1>, em .claude/skills/<nome1>/SKILL.md
✓ /<nome2>, em .claude/skills/<nome2>/SKILL.md

Pra usar: digite / e o nome em qualquer sessão.
Pra ajustar depois: edite o SKILL.md correspondente.
```

## Regras

- Não criar skill pra tarefa que aconteceu uma vez só. Tem que ser repetível.
- Máximo de 5 skills por sessão de mapeamento (se pedir mais, dividir em rodadas).
- Toda skill precisa de trigger claro na `description`: sem isso ela nunca é encontrada.
- Skill que depende de ferramenta que o usuário não tem (ex: API do Notion sem MCP) → avisar
  antes de criar e oferecer a versão simplificada.
