---
name: estrutura-projeto-agentes
description: >-
  Use sempre que for criar, organizar ou orientar tarefas num projeto local para
  o Cursor ou outro agente de código: garante AGENTS.md na raiz, .todo/README.md
  com checkbox e links só das tarefas abertas, e .docs/ com regras,
  arquitetura e design do projeto, todos referenciando uns aos outros.
---
# Estrutura de projeto para agentes (AGENTS.md + .todo/ + .docs/)

Regra do usuário, seguir à risca em todo projeto local. O assistente escreve, o Cursor local executa. Esta skill define **onde** cada coisa vive; o formato de cada tarefa segue a skill `instrucoes-para-cursor-local`.

## Estrutura obrigatória na raiz do projeto

```
<repo>/
├── README.md            # README principal do projeto (humanos)
├── AGENTS.md            # porta de entrada para qualquer agente (Cursor, etc.)
├── .todo/
│   ├── README.md        # único índice das tarefas abertas, com checkbox
│   ├── NN-nome-curto.md # uma tarefa por arquivo
│   └── .done/           # tarefas concluídas (movidas, nunca apagadas)
└── .docs/
    ├── README.md        # índice dos documentos do projeto
    ├── regras.md        # regras específicas do projeto
    ├── arquitetura.md   # decisões e limites de arquitetura a seguir
    └── design.md        # padrões de código, UI e design a seguir
```

O nome da pasta local deve ser idêntico ao nome do repo no GitHub.

## Onde ficam os projetos locais (regra do usuário)

No Windows do usuário (NBPITANG-491):

| Pasta | O que guarda |
|---|---|
| `C:\GIT\Z-ONE\<repo>` | projetos da Z-ONE, os principais |
| `C:\GIT\ZAPFCOORP\<repo>` | projetos menos importantes e testes |

Contas do GitHub: pessoal `hilderney`, org `zee-dash-one` (Z-ONE) e org `zapf-coorp`. Antes de escrever, confirme em qual das duas pastas o projeto está; se não estiver em nenhuma, pergunte ao usuário.

## O que cada arquivo faz

1. **`AGENTS.md` (raiz)**: regras que todo agente segue no projeto.
   - Ordem de leitura antes de qualquer trabalho: `AGENTS.md` → `.todo/README.md` → `.docs/README.md` e os docs que ele indicar → a tarefa.
   - Regras gerais: idioma (commits, branches, PRs e comentários em inglês), nunca gravar segredos (usar `.env` + `.env.example`), cuidados de shell do usuário, registrar cada comando e resultado, não abrir PR nem fazer merge sem o usuário pedir.
   - Ao concluir uma tarefa: registrar data e resultado no próprio arquivo da tarefa, tirar a linha dela do `.todo/README.md`, atualizar `.docs/` se a decisão mudou algo, mover o arquivo para `.todo/.done/` e apagar o que ficou obsoleto.
   - Mapa de arquivos (ver seção "Referências cruzadas").
   - Deve ser curto. Detalhe de projeto vai em `.docs/`, não aqui.
2. **`.todo/README.md`**: o único arquivo com links para as tarefas.
   - Lista de tarefas com checkbox, cada uma com link relativo: `- [ ] [03 - nome](./03-nome.md) (depende de 02)` e, quando concluída, `- [x] [03 - nome](./.done/03-nome.md) (concluída AAAA-MM-DD)`.
   - Só o que está **aberto**: tarefas pendentes e decisões pendentes do usuário. Nada de histórico longo nem registro do que já foi feito: o registro de tarefa concluída é o próprio arquivo dela em `.todo/.done/` (com status, data e resultado). O README só aponta para `.done/`.
   - Regras de execução das tarefas (substitui o antigo `00-LEIA-ME.md`; se ele existir, migrar o conteúdo para cá e mover o antigo para `.done/`).
3. **`.docs/`**: especificação viva do projeto, escrita de forma específica para cada projeto (não copiar genérico).
   - `regras.md`: regras de negócio e restrições do projeto.
   - `arquitetura.md`: stack, camadas, módulos, fluxos, o que não pode ser feito, decisões tomadas com data e motivo.
   - `design.md`: padrões de código (nomes, pastas, testes, lint) e, se houver interface, design system, cores, tipografia, componentes.
   - Pode ter mais arquivos se o projeto pedir (ex.: `api.md`, `deploy.md`), sempre listados no `.docs/README.md`.
4. **`README.md` principal**: descrição do projeto para humanos, como rodar e uma seção **Para agentes** apontando para `AGENTS.md`, `.todo/README.md` e `.docs/`.

## Referências cruzadas (obrigatório)

`README.md` principal, `AGENTS.md` e `.todo/README.md` trazem, cada um, uma tabela com **todos** esses arquivos: caminho, para que serve e quando ler. `.docs/README.md` traz o índice dos docs. **Somente `.todo/README.md` linka tarefas específicas**; os demais apontam para ele.

| Arquivo | Para que serve | Quando ler |
|---|---|---|
| `README.md` | visão geral e como rodar | primeiro contato |
| `AGENTS.md` | regras para agentes e ordem de leitura | antes de qualquer tarefa |
| `.todo/README.md` | tarefas abertas (links) e decisões pendentes | antes de executar |
| `.docs/README.md` | índice da especificação | antes de decidir algo |
| `.docs/regras.md` | regras do projeto | sempre |
| `.docs/arquitetura.md` | arquitetura a seguir | ao mexer em estrutura |
| `.docs/design.md` | padrões de código e design | ao escrever código/UI |

## Projeto sempre limpo (regra do usuário)

Projeto alinhado, sem lixo. Ao reorganizar ou concluir algo: substituir arquivos desatualizados (não criar cópias paralelas), apagar tarefas obsoletas ou já resolvidas e conteúdo que não vale mais, juntar tarefas sobrepostas. Pendências vivem em `.todo/README.md`, decisões vigentes em `.docs/`, e o que foi feito só em `.todo/.done/`. README principal não leva changelog nem histórico.

## Passos

1. Confirme o projeto e a pasta local (nome = repo). Pergunte ao usuário antes de alterar qualquer repo.
2. Leia o que já existe: README, código, `package.json` ou equivalente, `.todo/` e `.docs/` atuais.
3. Se faltar a estrutura, a **primeira tarefa** (`.todo/01-estrutura-agentes.md`) é o Cursor criar ou completar `AGENTS.md`, `.todo/README.md` e `.docs/` com base no que o assistente já levantou, sem inventar regras que o projeto não tem; o que for incerto fica marcado `[a confirmar com o usuário]`.
4. Escreva as tarefas seguintes conforme `instrucoes-para-cursor-local` e registre cada uma no `.todo/README.md` com checkbox e link.
5. Toda tarefa termina com: marcar checkbox, registrar o resultado no próprio arquivo da tarefa, atualizar `.docs/` se preciso, mover para `.todo/.done/`, corrigir o link.
6. Arquivos em UTF-8 sem BOM, com a assinatura do assistente no fim (bloco que a LLM deve ignorar).
7. Diga ao usuário quais arquivos foram criados e qual tarefa pedir ao Cursor primeiro.
