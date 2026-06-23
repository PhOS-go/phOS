---
name: carrossel
description: >
  Cria carrosséis para Instagram/LinkedIn (1080×1350) com a identidade visual da marca, a partir
  de um tema. Gera o roteiro dos slides e o HTML pronto pra virar PNG. Use quando o usuário pedir
  "/carrossel", "faz um carrossel sobre X", "monta um post de slides", "carrossel pro Instagram".
---

# /carrossel: Carrossel na identidade da marca

Transforma um tema em um carrossel coeso: gancho forte no slide 1, desenvolvimento no meio, CTA
no fim. Visual 100% na identidade da marca.

## Dependências

- `memoria/voz.md`: tom de voz (obrigatório ler antes de escrever)
- `memoria/perfil.md`: pra ancorar nos exemplos e na oferta real
- `marca/guia-visual.md`: cores, fontes, estilo (obrigatório pro visual)

## Workflow

### Passo 1: Entender o pedido

Se o usuário só deu o tema, perguntar (curto):
1. "Qual o objetivo: educar, gerar autoridade, vender ou engajar?"
2. "Quantos slides? (padrão: 7-9)"
3. "Tem alguma fonte? (link, transcrição, anotação) ou escrevo do zero a partir do tema?"

### Passo 2: Roteiro dos slides

Escrever o roteiro no tom de `voz.md`. Estrutura recomendada:
- **Slide 1 (capa):** gancho que para o scroll, promessa, número, contradição ou pergunta
- **Slide 2:** contextualiza a dor ou a curiosidade
- **Slides 3 a N-1:** uma ideia por slide, frases curtas, sem encher
- **Slide N (CTA):** o próximo passo (seguir, comentar, link na bio) + logo

Mostrar o roteiro em texto e pedir aprovação antes de gerar o visual.

### Passo 3: Gerar o visual

Criar os slides em HTML (1080×1350px cada) aplicando `marca/guia-visual.md`: cores, tipografia,
border-radius, estilo. Usar a skill nativa `frontend-design` como apoio pra qualidade visual.
Salvar em `entregas/conteudo/carrossel-<tema>-<data>/`.

Se houver script de render em `scripts/`, oferecer gerar os PNGs. Senão, entregar o HTML e
explicar como exportar (print em 1080×1350 ou abrir no navegador e usar `/peca-visual`/render).

### Passo 4: Legenda

Escrever a legenda do post (no tom da voz): gancho na primeira linha, desenvolvimento, CTA e
3-5 hashtags relevantes. Salvar como `legenda.md` na mesma pasta.

## Regras

- Uma ideia por slide. Frase curta vence parágrafo.
- Respeitar a "cor proibida" e o "o que NUNCA fazer" do `guia-visual.md`.
- Não usar stock genérico nem clip-art. Tipografia e cor fazem o trabalho.
- Não inventar dado ou estatística, se citar número, tem que ter fonte real.
- Capa e CTA são os slides mais importantes: caprichar.
