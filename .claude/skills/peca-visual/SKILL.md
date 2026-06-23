---
name: peca-visual
description: >
  Cria uma peça gráfica pontual, capa, banner, story, thumbnail, citação, na identidade visual
  da marca. Use quando o usuário pedir "/peca-visual", "faz uma capa/banner/story", "uma arte
  pra X", "thumbnail do vídeo", "imagem de citação".
---

# /peca-visual: Peça gráfica na identidade da marca

Peça única e rápida (não é carrossel, é uma imagem só). Capa de e-book, banner, story 1080×1920,
thumbnail de YouTube, card de citação. Sempre na identidade da marca.

## Dependências

- `marca/guia-visual.md`: cores, fontes, estilo (obrigatório)
- `memoria/voz.md`: pra qualquer texto na peça
- Skills nativas de apoio: `canvas-design` (PNG/PDF) e `frontend-design` (HTML→imagem)

## Workflow

### Passo 1: Definir a peça

Perguntar (curto, se não veio no pedido):
1. "Que peça é? (capa, banner, story, thumbnail, card de citação…)"
2. "Qual o formato/dimensão? (ou uso o padrão do tipo)"
3. "Qual o texto principal e o objetivo?"

Dimensões padrão por tipo: story 1080×1920 · post quadrado 1080×1080 · capa de e-book 1600×2560 ·
thumbnail YouTube 1280×720 · banner conforme o uso.

### Passo 2: Gerar

Criar a peça aplicando `marca/guia-visual.md`. Para PNG/PDF diretos, usar `canvas-design`; para
layouts mais ricos, montar em HTML com `frontend-design` e exportar. Salvar em
`entregas/pecas/<tipo>-<tema>-<data>/`.

### Passo 3: Variações

Oferecer 1-2 variações (ex: cor de fundo alternativa, com/sem logo) quando fizer sentido. Não
gerar dezenas, foco na que resolve.

## Regras

- Respeitar o `guia-visual.md`: um único destaque de cor, "cor proibida" fora, "o que NUNCA
  fazer" valendo.
- Texto curto e legível, hierarquia clara, contraste alto.
- Logo no lugar combinado (ver `guia-visual.md`).
- Sem stock genérico nem clip-art. Tipografia e cor carregam a peça.
