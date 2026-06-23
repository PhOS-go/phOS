# Catálogo de skills

Skills que o phOS pode reaproveitar em vez de reinventar. Use como referência ao criar comandos
novos com `/mapear-rotinas`, ou ative direto as que fizerem sentido pro seu projeto.

> Skills **globais** ficam em `~/.claude/skills/` e funcionam em qualquer projeto.
> Skills **locais** ficam em `.claude/skills/` e só funcionam neste projeto.

---

## Já incluídas no phOS

Os comandos de fábrica vivem em `.claude/skills/`:

**Núcleo:** `/instalar` · `/abrir` · `/salvar` · `/atualizar` · `/novo-projeto` · `/mapear-rotinas`
**Conteúdo & social:** `/carrossel` · `/calendario-editorial` · `/roteiro`
**Copy, vendas & lançamento:** `/landing-page` · `/email-venda` · `/lancamento`
**SEO & tráfego pago:** `/seo` · `/anuncio-google`
**Dados, relatórios & visual:** `/analisar-dados` · `/relatorio` · `/peca-visual`

---

## Nativas do Claude Code (já vêm prontas)

### Frontend Design
**O que faz:** cria interfaces web com design de alta qualidade, HTML/CSS/React que foge da
estética genérica de IA.
**Bom pra:** landing pages, dashboards, componentes, páginas de produto.
**Usada por:** `/landing-page`, `/carrossel`, `/peca-visual`.

### Canvas Design
**O que faz:** cria arte visual em PNG/PDF aplicando princípios de design, pôsteres, capas, peças.
**Bom pra:** capas de e-book, banners, thumbnails, peças gráficas.
**Usada por:** `/peca-visual`.

### PDF / DOCX / PPTX / XLSX
**O que faz:** manipula documentos, extrai/cria PDF, escreve Word, monta apresentações e planilhas.
**Bom pra:** propostas, contratos, relatórios formais, decks, planilhas.
**Usada por:** `/analisar-dados`, `/relatorio`.

### Webapp Testing
**O que faz:** testa aplicações web locais com Playwright, screenshots, verificação, logs.
**Bom pra:** testar uma landing antes de publicar, conferir responsividade.

### Skill Creator
**O que faz:** guia pra criar skills do zero, estrutura, triggers, teste.
**Bom pra:** quando `/mapear-rotinas` não cobre algo mais complexo.

---

## Recomendadas (instalar se fizer sentido)

### Copy de landing page
**O que faz:** escreve copy de página de vendas em blocos, com frameworks de conversão.
**Bom pra:** páginas de vendas de infoproduto, captura, ofertas.
**Usada por:** `/landing-page` (se instalada, ela é chamada em vez de escrever do zero).
**Como ativar:** instalar como skill global em `~/.claude/skills/`.

### Transcrição de YouTube
**O que faz:** extrai transcrição de vídeos do YouTube (precisa de `yt-dlp`).
**Bom pra:** virar vídeo em carrossel, roteiro ou newsletter.
**Usada por:** `/carrossel`, `/roteiro` (como fonte de conteúdo).

---

## Como adicionar uma skill a este catálogo

Testou uma skill e quer registrar pra referência futura? Copie o bloco:

```markdown
### Nome da skill
**O que faz:** [uma frase]
**Bom pra:** [casos de uso]
**Usada por:** [quais skills do phOS chamam ela, se for o caso]
**Como ativar:** [comando ou instrução]
```
