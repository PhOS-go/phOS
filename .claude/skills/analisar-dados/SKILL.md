---
name: analisar-dados
description: >
  Lê arquivos de dados (CSV, XLSX, PDF, planilha) e gera um resumo executivo com os achados que
  importam. Use quando o usuário pedir "/analisar-dados", "analisa essa planilha/CSV/PDF",
  "resume esses dados", "o que esses números dizem", "extrai os insights desse arquivo".
---

# /analisar-dados — Resumo executivo de dados

Pega um arquivo cru e devolve o que importa: os 3-5 achados que mudam uma decisão, não um dump de
estatística. Quem lê é uma pessoa ocupada que quer saber o que fazer com aquilo.

## Dependências

- `memoria/perfil.md` — pra interpretar os dados no contexto do negócio
- `memoria/foco.md` — pra destacar o que é relevante pro momento
- Skills nativas de apoio: `xlsx`, `pdf` (conferir `templates/skills/catalogo.md`)

## Workflow

### Passo 1 — Localizar o arquivo

Se o usuário não indicou, olhar em `dados/`. Confirmar qual arquivo analisar e qual a pergunta
por trás ("o que você quer saber com isso?"). Se não houver pergunta, fazer a análise
exploratória padrão.

### Passo 2 — Ler e entender

Ler o arquivo (CSV/XLSX/PDF). Entender as colunas, o período, a granularidade. Conferir
qualidade: linhas vazias, duplicatas, formato de data, outliers gritantes — e sinalizar.

### Passo 3 — Analisar

Buscar o que responde à pergunta do Passo 1:
- Totais e tendências (subiu/caiu, em quanto)
- Comparações relevantes (top/bottom, antes/depois)
- Anomalias e o que destoa
- Relação com o foco do negócio

### Passo 4 — Resumo executivo

Entregar em `entregas/relatorios/analise-<arquivo>-<data>.md`:

```
# Análise — [arquivo]

## O essencial (3-5 achados)
1. [achado que muda uma decisão]
...

## Números de apoio
[tabela curta com o que sustenta os achados]

## Recomendação
[o que fazer a partir disso — 1-3 ações]

## Ressalvas
[qualidade dos dados, o que não dá pra concluir]
```

## Regras

- Achado vem antes do número. Ninguém quer ler a planilha de novo, quer saber o que fazer.
- Não afirmar correlação como causa.
- Sinalizar limitação dos dados — não maquiar conclusão frágil.
- Se o arquivo estiver corrompido ou ilegível, dizer claramente em vez de inventar resultado.
