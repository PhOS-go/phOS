---
name: relatorio
description: >
  Gera um relatório de métricas (ex: semanal) a partir de exports de dados, com alertas e
  recomendações acionáveis. Use quando o usuário pedir "/relatorio", "relatório semanal",
  "relatório de métricas", "como foi a semana/mês", "relatório pro cliente".
---

# /relatorio: Relatório de métricas

Diferente do `/analisar-dados` (exploração de um arquivo solto), este é um relatório recorrente
de acompanhamento: compara com o período anterior, dispara alertas e recomenda ação. Bom pra
acompanhar conteúdo, vendas, tráfego ou o que o projeto medir.

## Dependências

- `memoria/perfil.md` e `memoria/foco.md`: pra saber quais métricas importam
- `marca/guia-visual.md`: se o relatório for pra cliente e precisar de visual
- Skills nativas de apoio: `xlsx`, `pdf`, `docx` (conferir catálogo)

## Workflow

### Passo 1: Definir o escopo

Perguntar (ou inferir do uso anterior):
1. "Período do relatório e com qual período comparar?"
2. "Quais métricas/canais entram? (ex: vendas, seguidores, tráfego, e-mail)"
3. "Pra você ou pra um cliente? (define o nível de formalidade e visual)"

### Passo 2: Reunir os dados

Ler os exports em `dados/` (ou os que o usuário indicar). Conferir que os períodos batem.

### Passo 3: Montar o relatório

Estrutura:

```
# Relatório: [período]

## Resumo (3 linhas)
[o que importa saber sem ler o resto]

## Métricas
| Métrica | Período | Anterior | Variação | Status |
|---------|---------|----------|----------|--------|

## 🟢 O que foi bem
## 🔴 Alertas
## → Recomendações
[1-3 ações concretas pro próximo período]
```

Salvar em `entregas/relatorios/relatorio-<periodo>.md`. Se for pra cliente, oferecer versão em
PDF/DOCX com a identidade da marca.

### Passo 4: Alertas

Destacar variações fortes (queda ou alta relevante), metas em risco e qualquer número que peça
ação imediata. Alerta sem recomendação não serve, sempre sugerir o próximo passo.

## Regras

- Comparar sempre com um período de referência, número solto não conta história.
- Variação relevante leva recomendação. Sem isso, é só um painel.
- Não maquiar resultado ruim. Relatório honesto é o que gera decisão certa.
- Se faltar dado pra uma métrica, marcar como "sem dados" em vez de estimar.
