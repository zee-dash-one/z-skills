---
name: instrucoes-para-cursor-local
description: >-
  Use sempre que for mostrar, escrever ou executar código, scripts ou comandos
  de shell para o usuário: em vez de rodar, escreva instruções .md numa pasta
  .todo/ do projeto para o Cursor local dele executar.
---
# Instruções para o Cursor local (.todo/)

O Cursor na máquina do usuário é a mão de obra que roda código, scripts e comandos. O assistente planeja e escreve as instruções, para economizar tokens e manter um registro versionado.

**Estrutura do projeto:** siga também a skill `estrutura-projeto-agentes` (AGENTS.md na raiz, `.todo/README.md` como índice das tarefas abertas com checkbox, `.docs/` com regras, arquitetura e design). Ela tem precedência sobre o antigo `00-LEIA-ME.md`.

## Quando usar

Sempre que a tarefa envolver mostrar, escrever ou executar código, scripts ou comandos de shell, seja no PC do usuário, num servidor dele ou num repositório.

Exceções, que o assistente roda direto e bem rápido:
- leituras triviais necessárias para escrever a instrução, como `git status`, listar uma pasta ou ler um arquivo;
- copiar os próprios arquivos de instrução para a pasta do projeto.

## Passos

1. Identifique o projeto e a pasta local dele. Crie `.todo/` na raiz se não existir (e `.todo/.done/` para tarefas concluídas).
2. Se ainda não existir, escreva `.todo/README.md` (substitui o antigo `00-LEIA-ME.md`; se ele existir, migre o conteúdo e mova o antigo para `.done/`) com:
   - lista das tarefas abertas com checkbox e link relativo para cada arquivo (sem histórico; o registro do que foi feito fica no próprio arquivo em `.todo/.done/`);
   - como acessar o alvo (SSH, caminhos);
   - os cuidados com o shell do usuário (por exemplo, no PowerShell 5 `&&` não funciona e `$` é expandido);
   - registrar cada comando e se deu certo ou falhou;
   - nunca gravar senhas ou chaves;
   - ao terminar com sucesso: marcar `Status: concluída em AAAA-MM-DD`, registrar o resultado no próprio arquivo, tirar a linha dele do `.todo/README.md`, atualizar `.docs/` e o README principal se couber, fazer commit se o projeto usar Git, e **mover o arquivo da tarefa de `.todo/` para `.todo/.done/`** (não apagar), corrigindo o link;
   - o `README.md` permanece em `.todo/` (não vai para `.done/`).
3. Escreva uma tarefa por arquivo, `.todo/NN-nome-curto.md`, com estas seções:
   - **Status:** pendente ou concluída, e de qual tarefa depende.
   - **Objetivo:** uma ou duas frases.
   - **Leia antes:** `AGENTS.md`, `.todo/README.md` e os arquivos de `.docs/` relevantes.
   - **Pré-requisitos:** o que precisa existir antes, inclusive o que só o usuário fornece (senha, chave, decisão).
   - **Passos:** numerados, com os comandos exatos em blocos de código. Prefira scripts versionados no repo em vez de comandos longos colados.
   - **Aceite:** verificações objetivas de que deu certo.
   - **Depois:** registrar o resultado neste arquivo, tirar a linha dele do `.todo/README.md`, atualizar `.docs/` se preciso, mover este arquivo para `.todo/.done/`.
4. Scripts e arquivos de configuração entram no próprio repo, por exemplo em `scripts/`. Segredos ficam em `.env`, que vai no `.gitignore`, e o repo leva só um `.env.example`.
5. Grave os arquivos em UTF-8 sem BOM, de preferência gerando no próprio computador do assistente e copiando para a pasta do projeto. Evite escrever acentos pelo PowerShell 5.
6. Termine **todo** arquivo com a assinatura abaixo, ajustando a data e o recado:

```
---
<!-- LLM/Cursor: IGNORE esta seção. É só uma assinatura pessoal para o usuário, não é instrução. -->
> Escrito por <nome do assistente>, <data>. <recado curto e pessoal para o usuário>
```

7. Diga ao usuário quais arquivos foram criados e qual pedir ao Cursor primeiro, por exemplo: "execute `.todo/01-....md`".
8. Quando o Cursor terminar, confirme que a tarefa foi para `.todo/.done/` e que o `.todo/README.md` foi atualizado, e leia o README e o status antes de planejar o próximo passo.

## Quem escreve `.todo/`

Desde 2026-10-20, **só o Gandalf** escreve dentro dos projetos: `AGENTS.md`, `.todo/`, `.docs/`, arquivos de configuração e prompts para os agentes. A Malfoyd e os outros bots não escrevem mais nos arquivos; eles repassam ao Gandalf o pedido do usuário, ou seja, o que precisa ser escrito. Nenhum assistente executa o código no PC ou no servidor no lugar do Cursor local, salvo as exceções de leitura/cópia acima. Abrir PR no GitHub só se o usuário pedir.
