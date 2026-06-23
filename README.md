# phOS

> O sistema operacional do seu trabalho dentro do Claude Code.

Você acabou de clonar o phOS. Em poucos minutos ele vai conhecer o seu projeto:
quem você é, como você fala, no que você está focado agora. A partir daí, toda
resposta sai com a sua cara e um punhado de comandos prontos faz conteúdo,
copy, lançamento, análise e organização rodarem com você no comando.

Não é mais uma ferramenta pra você abrir. É o sistema onde o seu trabalho roda.

---

## A ideia por trás

A maioria das pessoas usa IA como uma calculadora: pergunta, recebe, fecha,
esquece. Toda conversa começa do zero. Todo dia você reexplica quem você é, o que
faz, como gosta das coisas. O contexto vive espalhado em mil abas e na sua cabeça.

O phOS inverte isso. Ele dá ao Claude uma **memória que aprende com você** e
**comandos que executam do seu jeito**. Você corrige uma vez ele lembra pra
sempre. Você repete uma tarefa três vezes ele vira um comando. Quanto mais você
usa, mais o sistema fica do seu tamanho.

O resultado não é "fazer mais rápido". É **fazer sozinho o que antes exigia um
time** — com um sistema que não te substitui, vira parte de como você trabalha.

---

## Como ligar

Dois caminhos. Escolhe o que combina contigo.

### Pelo Claude (mais rápido)

Abre o Claude Code em qualquer pasta e cola:

```
Clona o https://github.com/PhOS-go/phOS.git na pasta atual,
entra nela e roda o /instalar.
```

Ele clona, entra na pasta nova e começa a entrevista de setup. Você só responde.

### Pelo terminal (mais previsível)

```
git clone https://github.com/PhOS-go/phOS.git
cd phOS
code .
```

Na janela do VS Code: terminal integrado → `claude` → `/instalar`.

> Quando o `/instalar` terminar, renomeia a pasta `phOS/` pro nome do seu projeto
> (fecha o VS Code, renomeia no Explorer/Finder, abre de novo). A pasta deixa de
> ser "phOS" — ela é o seu projeto agora.

O `/instalar` roda **uma vez só**. Te entrevista, monta a memória e configura o
sistema pelo seu perfil. Depois disso, é só usar.

---

## O mapa do sistema

```
memoria/    o cérebro — quem você é, como fala, no que está focado
marca/      o rosto — cores, fontes, logo (toda peça visual respeita)
entregas/   o resultado — conteúdo, copy, relatórios que as skills geram
dados/      o que entra — CSV, PDF, planilhas pra analisar
scripts/    utilitários do dia a dia
templates/  moldes de perfil, catálogo de skills e exemplos de marca
tarefas.md  o que está em jogo agora
```

---

## Os comandos

**Núcleo — operar o dia a dia**
`/abrir` carrega o contexto antes de cada sessão · `/salvar` faz commit + push no
GitHub · `/atualizar` varre o projeto e atualiza a memória · `/novo-projeto` cria
pasta isolada pra cada cliente ou iniciativa · `/mapear-rotinas` descobre o que
você repete e transforma em comando próprio.

**Conteúdo & social**
`/carrossel` monta carrosséis 1080×1350 com a sua identidade · `/calendario-editorial`
planeja a linha editorial · `/roteiro` transforma um tema em roteiro de vídeo/Reels.

**Copy, vendas & lançamento**
`/landing-page` escreve copy + estrutura de página de vendas · `/email-venda`
rascunha e-mails (ou sequências) de venda · `/lancamento` desenha o lançamento
inteiro: oferta, página, sequência e cronograma.

**Dados, relatórios & visual**
`/analisar-dados` lê CSV/XLSX/PDF e devolve resumo executivo · `/relatorio` lê
seus números e entrega relatório com alertas e recomendações · `/peca-visual`
cria capa, banner ou story na sua identidade.

---

## Como o phOS pensa

`memoria/` é o cérebro. Tudo que importa do seu projeto mora aqui — quem você é,
como fala, o que está em foco essa semana. O Claude lê antes de cada resposta.
Quanto melhor a memória, melhor o sistema.

`marca/` é o rosto. Cores, fontes, logo, estilo. Toda peça que o sistema gera
respeita isso.

`entregas/` e `scripts/` são o que sobra de concreto. O sistema produz, versiona
no GitHub, fica tudo seu.

E o sistema **aprende**: quando você corrige algo ou define uma preferência, ele
pergunta se quer salvar — e na próxima já vem certo.

---

## Primeiro dia

1. Rode `/instalar` (uma vez).
2. Renomeie a pasta pro nome do seu projeto.
3. No começo de cada sessão, rode `/abrir`.
4. Chame a skill que cabe na tarefa.
5. Ao terminar, `/salvar`.

Pronto. Você está rodando no phOS.
