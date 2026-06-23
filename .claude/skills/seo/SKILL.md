---
name: seo
description: >
  Roda um fluxo completo de SEO — pesquisa de palavras-chave, análise de concorrência, SEO
  on-page, pauta de conteúdo, SEO técnico e local, e plano de monitoramento. Use quando o usuário
  pedir "/seo", "otimizar pro Google", "ranquear", "pesquisa de palavra-chave", "SEO do site/blog",
  "aparecer no Google", "SEO local / Google Meu Negócio".
---

# /seo — Fluxo completo de SEO

Skill de processo, em etapas. Não despeja teoria — entrega decisões e artefatos prontos pra
executar. O usuário escolhe rodar o fluxo inteiro ou só a etapa que precisa.

## Dependências

- `memoria/perfil.md` — o que o negócio vende, pra quem, onde atua (essencial pra SEO local)
- `memoria/foco.md` — prioridade atual (qual página/produto ranquear primeiro)
- `memoria/voz.md` — tom do conteúdo otimizado
- Dados reais quando houver (volume de busca, posições) — via ferramenta/planilha em `dados/`.
  Sem dados reais, marcar estimativas como estimativas. Nunca inventar número de volume.

## Workflow (8 etapas)

Perguntar primeiro o escopo: "Rodar o fluxo inteiro ou uma etapa específica? E qual a página/
produto-alvo e a região (se o negócio for local)?"

### 1. Demanda — palavras-chave
Levantar termos por **intenção** (informacional, comercial, transacional). Organizar em:
termo principal, variações, cauda longa. Se houver dados de volume/dificuldade em `dados/`, usar;
senão, priorizar por lógica de intenção e marcar como estimativa.

### 2. Concorrência
Identificar quem ranqueia pros termos-alvo e o que eles fazem (formato, profundidade,
estrutura). Apontar a brecha — o ângulo que dá pra vencer.

### 3. SEO on-page
Pra a página-alvo, entregar: **title** (≤60 caracteres, com termo principal), **meta description**
(≤155, com CTA), estrutura de **H1/H2/H3**, sugestões de **interlinks**, **URL** limpa,
**alt text** das imagens.

### 4. Conteúdo
Gerar a **pauta otimizada**: título, termo-alvo, subtítulos (H2/H3), perguntas a responder
(People Also Ask), extensão sugerida e CTA. Se o usuário pedir, produzir o texto no tom de
`voz.md` (ou acionar `/roteiro`/`/carrossel` pra derivar conteúdo social do mesmo tema).

### 5. SEO técnico (checklist essencial)
Conferir o básico que trava ranqueamento: indexação, velocidade, mobile, HTTPS, sitemap,
dados estruturados (schema). Entregar como checklist com status e o que corrigir.

### 6. SEO local (se o negócio for local)
Otimização do **Perfil da Empresa no Google** (Google Business Profile): categoria, descrição,
serviços, fotos, horários, NAP consistente. Sugerir estratégia de avaliações.

### 7. Busca por IA (AEO/GEO)
Ajustes pra aparecer em respostas de IA e featured snippets: respostas diretas e objetivas,
FAQ estruturado, definições claras logo no início do conteúdo.

### 8. Monitoramento
Definir o que medir e com que frequência: posições dos termos-alvo, tráfego orgânico, cliques/
impressões (Search Console), conversões. Sugerir uma cadência de revisão (ex: mensal via `/relatorio`).

## Entrega

Salvar o resultado em `entregas/seo/seo-<alvo>-<data>.md`, organizado pelas etapas rodadas, com
um resumo no topo (3 ações prioritárias).

## Regras

- Intenção de busca vem antes de volume — termo certo com pouca busca vale mais que termo errado popular.
- Não prometer "primeira posição" nem prazo garantido. SEO é probabilístico.
- Não inventar volume/dificuldade. Sem dado real, dizer que é estimativa por intenção.
- Conteúdo otimizado ainda é conteúdo de gente — ler `voz.md`, não escrever pra robô.
- SEO local só entra se o negócio atende uma região física (conferir no `perfil.md`).
