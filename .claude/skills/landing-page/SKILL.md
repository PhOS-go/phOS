---
name: landing-page
description: >
  Cria a copy e a estrutura de uma página de vendas (landing page) alinhada à marca e à oferta do
  projeto. Reaproveita as skills de copy existentes e o frontend-design para o visual. Use quando
  o usuário pedir "/landing-page", "página de vendas", "copy da LP", "monta a landing", "texto da
  página de vendas".
---

# /landing-page: Página de vendas

Entrega a página de vendas em dois tempos: primeiro a copy (o que convence), depois o HTML (como
aparece). Não reescreve do zero o que o sistema já sabe fazer, orquestra as skills certas.

## Dependências e reuso

- `memoria/perfil.md`: a oferta, o público, os diferenciais reais
- `memoria/voz.md`: tom de voz
- `marca/guia-visual.md`: visual da página
- **Reuso de skills (não reimplementar):**
  - Copy de LP: se houver skill de copy de landing instalada (ex: `copy-lp-queiroz`), **usar ela**
    para gerar a copy em blocos. Conferir o catálogo em `templates/skills/catalogo.md`.
  - Visual/HTML: usar `frontend-design` (nativa) para construir a página.

## Workflow

### Passo 1: Briefing da oferta

Confirmar com o usuário (puxando o que já estiver no `perfil.md`):
1. Qual o produto/oferta e o preço
2. Pra quem é e qual a transformação principal
3. Prova (depoimentos, números, garantia)
4. Objetivo da página (venda direta, captura, agendamento)

### Passo 2: Copy

Gerar a copy chamando a skill de copy de LP disponível. Se não houver nenhuma, escrever a copy
em blocos nomeados: headline, subheadline, dor, solução, benefícios, prova, oferta, objeções,
garantia, urgência, FAQ, CTAs e PS. Sempre no tom de `voz.md`.

Mostrar a copy e pedir aprovação antes do visual.

### Passo 3: Página (HTML)

Construir a página com `frontend-design`, aplicando `marca/guia-visual.md` (cores, fontes,
botões, espaçamento). Página responsiva, CTA repetido em pontos estratégicos, hierarquia clara.

Salvar tudo em `entregas/copy/landing-<oferta>-<data>/` (copy em `.md`, página em `.html`).

### Passo 4: Revisão

Conferir: a promessa da headline bate com a oferta? O CTA é único e claro? A prova sustenta a
promessa? Sinalizar qualquer ponto fraco antes de entregar.

## Regras

- Não prometer o que a oferta não entrega, copy honesta converte e não gera reembolso.
- Reusar a skill de copy existente em vez de duplicar metodologia.
- Respeitar o `guia-visual.md`: nada de gradiente clichê de IA.
- Não inventar depoimento ou número. Prova fraca → sinalizar ao usuário, não fabricar.
