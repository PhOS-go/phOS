---
name: anuncio-google
description: >
  Monta uma campanha de Google Ads de ponta a ponta — estrutura, palavras-chave, negativas,
  anúncios responsivos (RSA), extensões e orçamento — e entrega em CSV pronto pra importar no
  Google Ads Editor. Use quando o usuário pedir "/anuncio-google", "campanha no Google Ads",
  "anúncio no Google", "tráfego pago no Google", "rodar Google Ads", "campanha de pesquisa".
---

# /anuncio-google — Campanha de Google Ads pronta pra importar

Entrega uma campanha estruturada e os arquivos CSV que o usuário importa direto no **Google Ads
Editor** — sem precisar montar tela por tela. Foco em campanhas de Pesquisa (Search); orienta
sobre Performance Max quando fizer sentido.

## Dependências

- `memoria/perfil.md` — oferta, ticket, público, região de atuação
- `memoria/foco.md` — o que priorizar (qual produto/oferta anunciar)
- `memoria/voz.md` — tom dos anúncios (dentro dos limites de caractere)

## Workflow

### Passo 1 — Briefing (entrevista)

1. "O que vamos anunciar (produto/oferta) e qual a página de destino (URL)?"
2. "Qual o objetivo: leads, vendas, ligações, tráfego?"
3. "Orçamento diário e região/idioma do público?"
4. "Tem conta no Google Ads e Google Ads Editor instalado? (o entregável é CSV pra importar lá)"

### Passo 2 — Estrutura da campanha

Definir: tipo (Search, na maioria dos casos), 2-4 **grupos de anúncios** temáticos (um por
intenção/produto), e a lógica de orçamento/lances (ex: Maximizar conversões com CPA-alvo quando
houver histórico; Maximizar cliques no início).

### Passo 3 — Palavras-chave

Por grupo de anúncios, listar palavras-chave com **tipo de correspondência**:
- `[correspondência exata]`
- `"correspondência de frase"`
- `correspondência ampla` (com cautela)

E uma lista de **palavras-chave negativas** (termos que desperdiçam verba — ex: "grátis",
"download", "vaga de emprego", conforme o caso).

### Passo 4 — Anúncios responsivos (RSA)

Pra cada grupo, escrever no tom de `voz.md`, respeitando os limites:
- **15 títulos** (até 30 caracteres cada) — variar benefício, termo-chave, CTA, prova
- **4 descrições** (até 90 caracteres cada)
- **Caminho de exibição** (2 campos de até 15 caracteres)

Conferir o limite de caracteres de cada item antes de entregar.

### Passo 5 — Extensões (assets)

Sugerir: **sitelinks** (4+), **frases de destaque** (callouts), **snippets estruturados**, e —
se fizer sentido — **extensão de chamada** e **de local**.

### Passo 6 — Entregar os CSVs

Gerar os arquivos no formato que o **Google Ads Editor** importa (uma planilha por entidade:
Campanhas, Grupos de anúncios, Palavras-chave, Anúncios RSA, Negativas, Extensões), salvos em
`entregas/ads/google-<oferta>-<data>/`. Incluir um `LEIA-ME.md` curto explicando como importar
(Google Ads Editor → Conta → Importar → selecionar os CSVs → revisar → publicar).

### Passo 7 — Acompanhamento

Definir os números a vigiar (CTR, CPC, conversões, CPA, taxa de conversão da página) e sugerir
revisão semanal via `/relatorio`. Listar critérios de ajuste (ex: pausar termo com gasto alto e
zero conversão).

## Regras

- Respeitar os limites de caractere do Google Ads — item estourado é item reprovado.
- Sempre incluir lista de negativas. Campanha sem negativa queima verba.
- Não prometer ROI/CPA específico — depende de leilão, página e oferta.
- Anúncio não pode prometer o que a página não entrega (afeta Índice de Qualidade e reprova).
- CSV tem que estar no formato do Google Ads Editor, não um CSV genérico.
