---
name: salvar
description: >
  Salva o trabalho do phOS no GitHub (commit + push). Na primeira vez, configura o repositório
  remoto. Use quando o usuário disser "salvar", "salva no github", "commit", "push", "/salvar",
  "fazer backup" ou pedir pra guardar o trabalho.
---

# /salvar: Salvar no GitHub

Skill de uma função só: garantir que o trabalho do usuário está no GitHub. Tem que ser fácil pra
quem nunca usou git.

## Workflow

### Primeira vez (repositório não inicializado)

Detectar com `git rev-parse --is-inside-work-tree`. Se falhar:

1. Conferir se git tem identidade configurada (`git config user.name` / `user.email`). Se não,
   perguntar nome e e-mail e configurar com `git config --global`.

2. Perguntar:
   > "Primeiro backup. Você já tem um repositório criado no GitHub pra esse projeto?
   > 1. Sim, me passa a URL (ex: https://github.com/usuario/nome.git)
   > 2. Não, me dá um nome que eu crio agora (ex: meu-projeto)"

3. **Opção 1:** `git init` → `git add .` → `git commit -m "Setup inicial do phOS"` →
   `git branch -M main` → `git remote add origin <URL>` → `git push -u origin main`.

4. **Opção 2:** conferir o `gh` CLI (`gh --version`).
   - Tem: `git init`, commit inicial, `gh repo create <nome> --private --source=. --push`.
   - Não tem: instruir a instalar o `gh` (https://cli.github.com/) ou criar o repo em
     github.com/new e voltar com a URL.

### Commits seguintes (já configurado)

1. `git status`. Sem mudanças → "Tá tudo sincronizado, nada novo." e parar.

2. Mostrar o `git status` curto e perguntar:
   > "Vou comitar tudo isso. Quer descrever a mudança em uma frase ou usa o resumo automático?"

3. Com mensagem do usuário, usar. Sem, gerar uma de 1 linha pelos arquivos alterados (ex:
   "Adiciona carrossel sobre X", "Atualiza memória", "Cria copy da landing").

4. `git add .` → `git commit -m "<mensagem>"` → `git push`.

5. Confirmar com o link (de `git remote get-url origin`):
   > "Salvo. Ver no GitHub: <URL>"

## Regras

- Nunca usar `--force` sem o usuário pedir explicitamente.
- Nunca rodar `git reset --hard` ou destrutivas sem confirmação clara.
- Push falhou por divergência (alguém comitou no remoto) → avisar e oferecer
  `git pull --rebase` antes de tentar de novo.
- Antes do primeiro push, lembrar de conferir o `.gitignore` se houver dados sensíveis em
  `dados/` (ex: planilhas com informação de cliente).
