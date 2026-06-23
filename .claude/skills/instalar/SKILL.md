---
name: instalar
description: >
  Instala o phOS no projeto do usuário. Faz uma entrevista curta sobre o projeto, o tom de
  voz, o foco atual e a identidade visual, e preenche memoria/perfil.md, memoria/voz.md,
  memoria/foco.md, marca/guia-visual.md e adapta o CLAUDE.md conforme o perfil escolhido.
  Use quando o usuário acabou de clonar o repositório e quer configurar o sistema, ou quando
  pedir explicitamente "rodar /instalar", "instalar o phOS", "primeiro setup", "configurar".
---

# /instalar: Configuração inicial do phOS

É o primeiro comando que o usuário roda depois de clonar o repositório. Não pode falhar e não
pode soar burocrático. Trate como uma conversa de descoberta: pergunte uma coisa por vez,
escute de verdade, não enfileire tudo de uma vez. O sistema tem que sair daqui sabendo quem é o
usuário, como ele fala e onde está o atrito do dia a dia.

## Pré-checagem

### 1. Nome da pasta

Conferir o nome da pasta atual (`basename "$(pwd)"`). Se for `phos`, `phOS`, `phOS-main`,
`phos-main` ou variação genérica, avisar que no fim vamos renomear:

> "Reparei que a pasta ainda tem nome genérico ('<nome-atual>'). O ideal é ela ter o nome do
> seu projeto, não 'phOS'. Quando terminarmos, te lembro de renomear, é rápido. Bora?"

Guardar o nome atual pra usar na Fase 5.

### 2. Arquivos de contexto

Conferir se algum arquivo de memória já está preenchido (não é placeholder):
`memoria/perfil.md`, `memoria/voz.md`, `memoria/foco.md`, `marca/guia-visual.md`.

Se algum já tiver conteúdo real, perguntar:
> "Já tem contexto preenchido aqui. Quer recomeçar do zero (sobrescrever) ou só completar o que
> falta?"

Se for setup limpo, seguir direto. (Obs: `marca/guia-visual.md` vem com a identidade do phOS
como exemplo, isso conta como placeholder e pode ser sobrescrito.)

## Fase 0: Idioma

Perguntar em que língua o usuário quer operar (padrão: português). Registrar, todas as skills
respondem nessa língua.

## Fase 1: Perfil

Perguntar qual perfil mais combina. As descrições importam: a confusão mais comum é entre
"Criador solo" e "Freelancer", então deixe a diferença explícita.

1. **Criador solo**: você é uma pessoa só e o ativo principal é a SUA marca/audiência. Produz e
   publica pra você mesmo (conteúdo, produtos próprios). Não trabalha por encomenda pra clientes.
2. **Freelancer**: você é uma pessoa só, mas atende CLIENTES (trabalho por projeto/encomenda). Se
   você "faz X pra clientes", é aqui, não em Criador solo.
3. **Agência / consultoria**: equipe pequena entregando pra vários clientes.
4. **Empresa**: empresa estabelecida com setores (marketing, comercial, etc.).

Regra prática pra desempatar: trabalha PRA clientes? Freelancer (ou Agência, se tiver equipe).
Trabalha só pra própria marca? Criador solo.

A resposta define qual molde de `CLAUDE.md` aplicar (ver `templates/perfis/`). Se o usuário tem
um projeto pessoal não-comercial, usar o molde "solo" e adaptar.

**Conferência de perfil:** se a entrevista (perguntas 2 e 3) revelar um trabalho que não bate com
o perfil escolhido (ex: escolheu "Criador solo" mas descreve atender clientes), apontar
gentilmente, explicar a diferença prática e sugerir o perfil que encaixa melhor ANTES de
preencher os arquivos. Confirmar com o usuário e seguir com o perfil corrigido.

## Fase 2: Entrevista

Fazer as perguntas em ordem, esperando cada resposta. Se vier resposta vaga, pedir concretude
uma vez só, depois registrar o que veio.

**Sobre o projeto:**
1. "Como você chama o que você faz? (nome do negócio, ou seu nome se for marca pessoal)"
2. "O que você entrega, em uma frase do jeito que falaria pro vizinho?"
3. "Quem te paga, ou, se for projeto pessoal, qual o objetivo? (descreva em uma ou duas frases, sem persona genérica)"
4. "Você toca sozinho ou tem equipe? Se tem, quantos e cada um fazendo o quê?"

**Sobre a voz:**
5. "Me cola um exemplo da sua escrita, uma legenda, um e-mail, qualquer coisa real e recente. Assim eu calibro o jeito de escrever sem adivinhar."
6. "O que te dá ranço quando alguém escreve? (ex: 'vamos juntos!', emoji em e-mail formal, 'caro cliente', jargão de guru, 'alavancar')"

**Sobre o foco:**
7. "Qual o gargalo do projeto hoje? O que está segurando ele de crescer?"
8. "Se eu pudesse tirar UMA coisa que você repete toda semana das suas costas, qual seria?"

**Sobre a marca:**
9. "Você tem identidade visual definida ou está no zero? Se tem, me passa as cores principais e a fonte."
10. "Tem logo? Se sim, joga o arquivo em `marca/logo.png` (ou `.svg`) e me confirma."

## Fase 3: Preencher os arquivos

### `memoria/perfil.md`
Preencher com as respostas 1-4. Formato simples: nome/projeto, o que é, o que entrega, quem
paga/objetivo, equipe, ferramentas, principais entregas.

### `memoria/voz.md`
Preencher com as respostas 5-6:
- **Tom de voz:** derivar do exemplo real da pergunta 5 (2-3 frases descrevendo o jeito, com referência ao exemplo)
- **O que evitar:** lista direta da resposta 6
- **Estilo geral:** síntese do que combina e do que destoa
- **Exemplo de referência:** colar o trecho da pergunta 5

### `memoria/foco.md`
Preencher com as respostas 7-8:
- **Fase atual:** inferir do contexto
- **Prioridade principal:** o que ataca o gargalo direto
- **Gargalo:** resposta 7
- **A tirar das costas:** resposta 8, marcar como candidata a virar skill via `/mapear-rotinas`

### `marca/guia-visual.md`
Se o usuário deu cores/fontes/logo (perguntas 9-10), sobrescrever a identidade-exemplo do phOS
com a marca dele. Se não tem identidade ainda, avisar:
> "Mantive a identidade-exemplo no `marca/guia-visual.md`. Quando você definir a sua marca, edita
> lá, as skills de carrossel, peça e landing leem esse arquivo antes de criar qualquer visual."

### `CLAUDE.md`
Pegar o molde do perfil escolhido na Fase 1 (`templates/perfis/claude-md-<perfil>.md`), adaptar
com o nome do projeto e a estrutura mencionada nas respostas, e **acrescentar** o conteúdo
abaixo da linha-marcador `<!-- O /instalar acrescenta abaixo… -->` no `CLAUDE.md` da raiz (não
apagar as regras de operação que já estão em cima).

## Fase 4: Resumo

```
✓ Idioma: [idioma]
✓ Perfil: [perfil]
✓ Projeto: memoria/perfil.md
✓ Voz: memoria/voz.md
✓ Foco: memoria/foco.md
✓ Marca: marca/guia-visual.md  [sua marca | identidade-exemplo, preencher depois]
✓ CLAUDE.md adaptado pro perfil [perfil]
```

## Fase 5: Renomear a pasta (se necessário)

Se a pasta ainda tem nome genérico, gerar slug do nome do projeto (resposta 1): minúsculas, sem
acentos, espaços viram hífen, especiais removidos. Ex: "Acme Estúdio" → `acme-estudio`.

> "Última coisa: a pasta ainda está como '<nome-atual>'. Pra ter cara do seu projeto, recomendo
> renomear pra '<slug>'.
>
> 1. Feche o VS Code
> 2. Renomeie a pasta no Explorer/Finder (ou no terminal fora dela: `mv <nome-atual> <slug>`)
> 3. Abra o VS Code de novo na pasta renomeada
>
> Se preferir outro nome, me fala que eu ajusto."

Se a pasta já tem nome próprio, pular esta fase.

## Fase 6: Próximos passos

> "Pronto. O phOS já te conhece.
>
> No começo de cada sessão, rode `/abrir`: eu carrego tudo que combinamos antes da primeira
> frase. Pra qualquer tarefa (carrossel, landing, lançamento, análise), é só chamar a skill que
> cabe.
>
> Você falou que repete '<resposta 8>' toda semana. Quando quiser tirar isso das costas de vez,
> roda `/mapear-rotinas` que eu transformo em comando próprio."

Se quiser publicar no GitHub, mencionar `/salvar`.

## Regras

- Não inventar dados. Resposta vaga → registrar como veio, ou deixar placeholder claro.
- Não escrever "este arquivo será preenchido pelo /instalar" nos arquivos finais, esse aviso só
  vive nos placeholders e sai depois do setup.
- O setup dura 5-7 minutos no máximo. Se o usuário enrolar numa pergunta, registre o que tem e
  siga.
- Não fazer perguntas extras além das listadas sem motivo claro.
