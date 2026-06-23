---
name: atualizar
description: >
  Varre o projeto e atualiza a memória do phOS (perfil, voz, foco) com o que mudou desde a
  última vez. Use quando o usuário disser "/atualizar", "atualiza a memória", "revisar contexto",
  "muita coisa mudou" ou ao perceber que o contexto ficou desatualizado.
---

# /atualizar — Varredura e atualização da memória

Skill de manutenção. O dia a dia muda mais rápido do que a memória — esta skill reconcilia as
duas coisas, de forma controlada (sempre mostrando antes de salvar).

## Workflow

### Passo 1 — Ler o estado atual

Ler `memoria/perfil.md`, `memoria/voz.md`, `memoria/foco.md` e `marca/guia-visual.md` pra ter o
retrato atual da memória.

### Passo 2 — Varrer sinais de mudança

Olhar o que o projeto revela que a memória ainda não registrou:
- Pastas novas em `entregas/`, `projetos/` ou `clientes/` → cliente ou iniciativa nova
- Skills novas em `.claude/skills/` que não estão refletidas no `CLAUDE.md`
- `tarefas.md` com itens que mudaram o foco
- Histórico recente do git (`git log --oneline -20`, se houver repo) pra ver no que se trabalhou

### Passo 3 — Propor as atualizações

Listar o que parece desatualizado, em formato de diff de uma linha cada, agrupado por arquivo:

```
memoria/perfil.md
  + Cliente novo: [nome] (detectado em entregas/clientes/...)

memoria/foco.md
  ~ Prioridade mudou de [antiga] pra [nova]?

CLAUDE.md
  + Skill nova /<nome> criada — registrar na lista de comandos
```

Perguntar:
> "Encontrei isso. Quais dessas atualizações você quer que eu aplique? (todas, algumas ou
> nenhuma)"

### Passo 4 — Aplicar as aprovadas

Editar só as linhas aprovadas. Não reformatar o arquivo inteiro. Confirmar o que foi salvo.

## Regras

- Nunca sobrescrever sem confirmação — esta skill propõe, o usuário decide.
- Não inventar mudança que não tem evidência no projeto.
- Se nada mudou, dizer "Memória já está em dia" e parar.
- Não confundir entrega pontual (um post avulso) com mudança de contexto — só propor o que tem
  valor duradouro.
