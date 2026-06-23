---
name: email-venda
description: >
  Escreve e-mails de venda, um avulso ou uma sequência, no tom da marca, com assunto, corpo e
  CTA. Use quando o usuário pedir "/email-venda", "e-mail de venda", "sequência de e-mails",
  "escreve um e-mail pra vender X", "campanha de e-mail".
---

# /email-venda: E-mail(s) de venda

Escreve e-mail que abre, é lido e clica. Funciona tanto pra um disparo único quanto pra uma
sequência de lançamento/nutrição.

## Dependências

- `memoria/voz.md`: tom (e-mail é conversa, não folheto)
- `memoria/perfil.md`: oferta, público, prova
- `memoria/foco.md`: pra encaixar no momento (lançamento? nutrição?)

## Workflow

### Passo 1: Definir o escopo

Perguntar (curto):
1. "Um e-mail só ou uma sequência? Se sequência, quantos e com qual objetivo (lançamento, carrinho, nutrição, reengajamento)?"
2. "Qual a oferta/ação que esse(s) e-mail(s) leva(m)?"
3. "Pra qual lista? (clientes, leads frios, abandono de carrinho…)"

### Passo 2: Escrever

Pra cada e-mail entregar:
- **Assunto:** 2-3 opções (curto, curioso ou direto, testar)
- **Preview text:** a linha que aparece depois do assunto
- **Corpo:** abertura que prende, uma ideia central, CTA claro
- **CTA:** um só, repetido no máximo duas vezes

Se for sequência, desenhar o arco: cada e-mail tem um papel (ex: 1 história/dor, 2 solução,
3 prova, 4 oferta, 5 urgência) e referencia o anterior sem repetir.

### Passo 3: Entregar

Salvar em `entregas/copy/emails-<campanha>-<data>.md`, um bloco por e-mail, com uma linha de
cabeçalho indicando quando enviar cada um (se for sequência).

## Regras

- Tom de gente, não de empresa. Ler `voz.md` antes.
- Um CTA por e-mail. Confusão mata clique.
- Assunto não pode prometer o que o corpo não entrega (clickbait queima lista).
- Não inventar urgência falsa ("últimas vagas" sem ser verdade), sinalizar ao usuário.
- E-mails curtos vencem. Cortar tudo que não empurra pro CTA.
