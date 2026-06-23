---
name: abrir
description: >
  Abre uma sessão de trabalho carregando a memória do projeto (perfil, voz, foco e marca) e
  devolve um resumo curto pro usuário começar. Use quando o usuário disser "abrir", "começar o
  dia", "/abrir", "vamos trabalhar" ou no primeiro turno de uma sessão depois do /instalar.
---

# /abrir: Abertura de sessão

Curto e direto. O objetivo é carregar o contexto e devolver uma síntese de uma frase pra o
usuário começar a trabalhar.

## Workflow

1. Ler, em ordem:
   - `memoria/perfil.md`
   - `memoria/voz.md`
   - `memoria/foco.md`
   - `marca/guia-visual.md` (só pra saber se está preenchido com a marca do usuário ou ainda na identidade-exemplo)

2. Se algum dos três primeiros (`perfil`, `voz`, `foco`) ainda for placeholder, responder e
   parar:
   > "Vi que `memoria/<arquivo>.md` ainda não foi preenchido. Quer rodar `/instalar` agora?"

3. Se tudo estiver preenchido, devolver UMA mensagem curta neste formato:

```
[Nome do projeto], [o que faz em 5-8 palavras]
Foco: [prioridade principal do foco.md, em uma frase]
Tom: [resumo de 3-4 palavras da voz]

Pronto. O que vamos fazer hoje?
```

4. Não listar quais arquivos foram lidos. Não confirmar leitura. Só usar o contexto.

## Regras

- A resposta cabe em até 5 linhas no terminal.
- Não fazer perguntas além de "o que vamos fazer?".
- Se o `marca/guia-visual.md` ainda estiver na identidade-exemplo do phOS, não mencionar, isso
  só vira assunto quando uma skill visual for chamada.
- Se o `foco.md` indicar algo com prazo próximo, pode incluir um aviso de uma linha (ex:
  "Lembrete: entrega de X vence sexta").
