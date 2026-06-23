# phOS: regras de operação

Este arquivo é o coração do sistema. Ele define como o Claude opera dentro do
phOS: como lê o contexto, aprende com correções, mantém a memória em dia e cria
comandos novos conforme o trabalho evolui.

O arquivo é editável. Quando o `/instalar` roda, ele acrescenta no final desta
página as regras específicas do seu projeto (a partir do molde de perfil escolhido).

---

## 1. Carregar o contexto

No início de toda conversa, ler os seguintes arquivos (quando existirem e
estiverem preenchidos, não placeholder):

1. `memoria/perfil.md`: quem é o usuário, o que faz, como funciona o projeto
2. `memoria/voz.md`: tom de voz, estilo de escrita, o que evitar
3. `memoria/foco.md`: fase atual, prioridades, prazos

Usar isso como base de qualquer resposta ou decisão. Ao sugerir prioridades,
formatos ou caminhos, considerar sempre o foco atual descrito em `foco.md`.

Para qualquer tarefa visual (carrossel, peça, landing page), consultar antes
`marca/guia-visual.md` como referência de estilo.

Não listar o que foi lido nem confirmar a leitura. Só usar o contexto com
naturalidade.

---

## 2. Usar as skills

Antes de executar qualquer tarefa, verificar se existe skill relevante em
`.claude/skills/`. Se existir, seguir o workflow dela. Se não existir, executar
normalmente.

Ao concluir uma tarefa que não tinha skill mas parece repetível (o usuário
provavelmente vai pedir de novo), perguntar:

> "Isso tem cara de virar comando pra próxima vez. Quer que eu crie?"

Só perguntar quando o padrão de repetição for claro. Não perguntar pra tarefas
pontuais ou perguntas soltas.

---

## 3. Aprender com correções

Quando o usuário corrigir algo, melhorar uma resposta ou dar uma instrução com
cara de permanente (frases como "na real é assim", "não faz mais isso", "prefiro
assim", "sempre que…", "evita…", "da próxima vez…"), perguntar:

> "Quer que eu guarde isso pra não precisar repetir?"

Se sim, salvar no lugar certo:

- **Sobre o projeto/negócio** (clientes, oferta, mercado) → `memoria/perfil.md`
- **Sobre voz e estilo** (tom, formato, o que evitar) → `memoria/voz.md`
- **Sobre prioridades e foco** (metas, prazos) → `memoria/foco.md`
- **Regra de comportamento desta pasta** → o próprio `CLAUDE.md`

Salvar como uma linha nova clara, sem reformatar o arquivo inteiro. Confirmar
mostrando a linha que foi adicionada.

Não perguntar quando a correção for óbvia do contexto imediato (ex: "na verdade o
arquivo se chama X"). Só quando a informação tiver valor duradouro.

---

## 4. Manter a memória em dia

Ao terminar uma tarefa que mudou algo relevante (cliente novo, skill nova,
mudança de foco, processo novo, ferramenta conectada, estrutura alterada),
perguntar:

> "Isso mexeu no seu contexto. Quer que eu atualize a memória?"

Se sim, atualizar onde faz sentido:

- **Cliente, oferta, ferramenta, equipe** → `memoria/perfil.md`
- **Mudança de prioridade ou foco** → `memoria/foco.md`
- **Tom ou estilo** → `memoria/voz.md`
- **Pasta, regra de organização, skill criada** → `CLAUDE.md`
- **Visual (cores, fontes, logo)** → `marca/guia-visual.md`

Mostrar o que vai mudar antes de salvar. Não reformatar o arquivo inteiro, só
adicionar ou editar a linha relevante.

**Quando NÃO perguntar:**
- Tarefas pontuais sem impacto no contexto (um e-mail avulso, um post)
- Perguntas simples ou conversa sem ação
- Mudanças já salvas pela regra 3 (aprender com correções)

> Dica: rode `/atualizar` pra uma varredura completa quando estiver na dúvida.

---

## 5. Criar skills novas

Quando o usuário pedir uma skill nova:

1. Verificar se existe molde relevante em `templates/skills/catalogo.md`. Se uma
   skill nativa ou recomendada já resolve, sugerir ela em vez de criar do zero.
2. Perguntar se é específica deste projeto ou útil em qualquer um:
   - Específica → `.claude/skills/<nome>/SKILL.md` (local)
   - Universal → `~/.claude/skills/<nome>/SKILL.md` (global)
3. Ler `memoria/perfil.md` e `memoria/voz.md` pra calibrar a skill ao contexto.
4. Se a skill precisar de arquivos de apoio (moldes, exemplos), criar dentro da
   pasta da skill.
5. Garantir frontmatter com `name` e `description` (a `description` precisa dizer
   *quando* a skill é invocada, sem isso ela nunca é encontrada). O `name` tem
   que ser igual ao nome da pasta.

---

## 6. Princípios

- Não inventar dados. Se faltar informação, perguntar ou deixar placeholder claro.
- Nunca rodar comandos destrutivos de git (`reset --hard`, `push --force`) sem o
  usuário pedir explicitamente.
- Falar a língua do usuário (definida no `/instalar`) e no tom de `memoria/voz.md`.
- Entregar o trabalho em `entregas/` com nome e data claros, salvo instrução
  diferente no perfil.

---

<!-- O /instalar acrescenta abaixo desta linha as regras específicas do seu projeto. -->
