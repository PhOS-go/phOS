---
name: novo-projeto
description: >
  Cria uma pasta de projeto nova com CLAUDE.md dedicado, depois de uma entrevista curta sobre o
  projeto (cliente, objetivo, entregas previstas). Use quando o usuário disser "novo projeto",
  "novo cliente", "/novo-projeto", "começar projeto pra X" ou pedir pra estruturar um trabalho novo.
---

# /novo-projeto — Pasta de projeto com contexto dedicado

Quando o usuário começa um trabalho novo (cliente, iniciativa, produto), cria uma pasta com
`CLAUDE.md` próprio que herda o contexto da raiz e adiciona o que é específico do projeto.

## Workflow

### Passo 1 — Entrevista (4 perguntas)

1. "Qual o nome do projeto ou cliente?"
2. "É um cliente novo, projeto interno ou iniciativa pessoal?"
3. "Qual o objetivo principal? (uma frase)"
4. "Que tipo de entrega vai ter? (ex: conteúdo, landing, lançamento, automação — pode ser mais de uma)"

### Passo 2 — Decidir o local

Baseado na resposta 2 (conferir a convenção no `CLAUDE.md` da raiz, que varia por perfil):
- **Cliente novo:** `clientes/<Nome>/`
- **Projeto interno:** `projetos/<nome>/` (criar `projetos/` se não existir)
- **Iniciativa pessoal:** perguntar onde o usuário prefere

### Passo 3 — Estrutura

Criar a pasta com:
- `CLAUDE.md` do projeto (herdado + específico)
- `briefing.md` (com o que foi coletado)
- Subpastas conforme as entregas mencionadas (ex: mencionou "conteúdo e landing" → `conteudo/` e `landing/`)

### Passo 4 — CLAUDE.md do projeto

```markdown
# [Nome do projeto]

> Pasta dedicada, criada em [data]. As instruções aqui sobrescrevem as da raiz quando relevantes.

## Sobre
[Objetivo da resposta 3]

## Tipo
[Cliente novo / Projeto interno / Iniciativa pessoal]

## Entregas previstas
- [entrega 1]
- [entrega 2]

## Onde salvar o quê
- Briefing e contexto: nesta pasta
- Entregas: cada subpasta criada

## Herda da raiz
Este projeto herda tom de voz, marca e contexto definidos em `memoria/` e `marca/` da raiz.
Não duplicar essas informações aqui.

## Específico deste projeto
[Vazio — preencher com regras que valem só aqui, conforme descobrir]
```

### Passo 5 — Resumo

```
Pasta criada: [caminho]
✓ CLAUDE.md do projeto
✓ briefing.md
✓ Subpastas: [lista]

Quando for trabalhar nele, abra o terminal já dentro da pasta — assim eu carrego o CLAUDE.md
específico junto com o da raiz.
```

## Regras

- Nome de pasta: usar como o usuário falou (manter acentos, espaços viram hífen, nome reconhecível).
- Não criar subpastas que não foram pedidas "pra organizar melhor". Só o que foi mencionado.
- Pasta com mesmo nome já existe → avisar e perguntar se adiciona dentro ou cria com sufixo.
