---
name: calendario-editorial
description: >
  Planeja um calendário editorial de conteúdo (semanal ou mensal) alinhado ao foco do projeto:
  temas, formatos, ganchos e datas. Use quando o usuário pedir "/calendario-editorial",
  "planejar conteúdo", "calendário de posts", "linha editorial", "o que postar essa semana/mês".
---

# /calendario-editorial: Planejamento de conteúdo

Transforma o foco do projeto em um plano de conteúdo concreto: o que postar, em que formato,
com que gancho e quando. Não é só uma lista de temas, é uma linha editorial com intenção.

## Dependências

- `memoria/perfil.md`: quem é a audiência, o que se entrega
- `memoria/foco.md`: prioridade atual (o conteúdo serve o foco)
- `memoria/voz.md`: tom dos ganchos

## Workflow

### Passo 1: Definir o escopo

Perguntar (curto):
1. "Período: semana ou mês?"
2. "Quantos posts por semana e em quais canais? (Instagram, LinkedIn, YouTube, e-mail…)"
3. "Tem algum objetivo no período? (lançamento, autoridade, engajamento, nutrição)"

### Passo 2: Definir os pilares

A partir do `perfil.md` e `foco.md`, propor 3-4 **pilares de conteúdo** (temas-mãe recorrentes
que sustentam o posicionamento). Confirmar com o usuário.

### Passo 3: Montar o calendário

Distribuir os posts pelos pilares e pelas datas, variando formato e intenção. Pra cada post:

| Data | Canal | Formato | Pilar | Gancho | Objetivo | CTA |
|------|-------|---------|-------|--------|----------|-----|

Equilibrar: conteúdo de topo (alcance), de meio (autoridade/relação) e de fundo (venda). Evitar
repetir formato em dias seguidos.

### Passo 4: Entregar

Salvar em `entregas/conteudo/calendario-<periodo>-<data>.md`, com a tabela + uma nota de uma
linha explicando a lógica do período. Oferecer já gerar uma das peças (ex: `/carrossel` ou
`/roteiro` do primeiro item).

## Regras

- Todo post serve o foco atual, nada de tema solto sem ligação com a estratégia.
- Gancho é obrigatório em cada item (não basta o tema).
- Não encher de posts: melhor um calendário executável que um irreal.
- Marcar quais itens dependem de outras skills do phOS pra produzir.
