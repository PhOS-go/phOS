---
name: lancamento
description: >
  Desenha um lançamento de produto de ponta a ponta: oferta, página, sequência de conteúdo e
  e-mails, e cronograma. Orquestra as outras skills do phOS. Use quando o usuário pedir
  "/lancamento", "planejar um lançamento", "vou lançar X", "estrutura de lançamento", "campanha de venda".
---

# /lancamento: Estrutura de lançamento

Skill orquestradora. Não faz tudo sozinha, desenha o plano e chama as outras skills do phOS pra
produzir cada peça (`/landing-page`, `/email-venda`, `/carrossel`, `/calendario-editorial`).

## Dependências

- `memoria/perfil.md`: produto, público, oferta
- `memoria/foco.md`: datas e prioridade
- `memoria/voz.md`: tom de tudo que for escrito

## Workflow

### Passo 1: Briefing do lançamento (entrevista)

1. "O que está sendo lançado e qual o preço?"
2. "Pra quem? (lista existente, tráfego frio, audiência orgânica)"
3. "Tem data de abertura e fechamento de carrinho?"
4. "Qual o modelo: lançamento semente, perpétuo, evento ao vivo, ou simples (abre e fecha)?"
5. "O que você já tem pronto (página, e-mails, audiência) e o que falta?"

### Passo 2: Desenhar a oferta

Estruturar a oferta de forma clara: produto + bônus + garantia + preço + ancoragem. Validar a
"promessa central", a transformação que justifica o preço.

### Passo 3: Montar o mapa do lançamento

Entregar um plano com fases e datas:
- **Pré-lançamento:** conteúdo de aquecimento (chamar `/calendario-editorial` e `/carrossel`)
- **Abertura:** página no ar (`/landing-page`) + e-mail/conteúdo de abertura
- **Carrinho aberto:** sequência de e-mails (`/email-venda`) + conteúdo de prova/objeção
- **Fechamento:** e-mails de urgência + última chamada

Apresentar como cronograma (tabela data × peça × skill responsável × status).

### Passo 4: Produzir as peças

Perguntar por onde começar e ir chamando as skills correspondentes pra produzir cada item.
Salvar tudo numa pasta única do lançamento: `entregas/copy/lancamento-<nome>-<data>/`.

### Passo 5: Checklist final

Antes da abertura, rodar um checklist: página testada, e-mails agendados, links certos, prova
no lugar, oferta clara. Listar o que ainda falta.

## Regras

- É orquestradora: reusar as skills do phOS em vez de reescrever copy/página do zero.
- Tudo do lançamento vive numa pasta só, pra não espalhar.
- Cronograma realista, melhor um lançamento simples bem executado que um complexo pela metade.
- Não fabricar escassez falsa. Urgência tem que ser real (data de fechamento de verdade).
