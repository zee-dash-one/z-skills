---
name: opencode-cron-tarefas
description: >-
  Use quando o Hil pedir para criar, agendar, listar, buscar, alterar ou remover
  tarefas repetitivas (cron) para o agente OpenCode rodar como usuário melchior.
  Ensina o registro em JSON, o local padrão das tarefas e como instalar/atualizar
  a entrada no crontab do melchior.
---
# Tarefas repetitivas (cron) do OpenCode — melchior

Esta skill define como agendar e gerenciar tarefas repetitivas para o agente OpenCode executar como usuário `melchior` no `z-server-01`, usando o **crontab do melchior** e um registro de tarefas em **arquivos JSON**.

## Local padrão (sempre pesquisar aqui)

- **Tarefas (JSON):** `~/.config/opencode/cron/tasks/` (1 arquivo `.json` por tarefa)
- **Runner:** `~/.config/opencode/cron/run-task.sh`
- **Logs:** `~/.config/opencode/cron/logs/` (um arquivo por execução)
- **Execuções/artefatos:** `~/.config/opencode/cron/runs/`

> Sempre que o Hil perguntar sobre tarefas agendadas (quais existem, status, detalhes, horários, prompts), **pesquise em `~/.config/opencode/cron/tasks/`** e mostre o conteúdo relevante. Se precisar confirmar o agendamento ativo, confira também `crontab -l` do `melchior`.

## Formato do JSON (1 arquivo por tarefa)

Arquivo: `~/.config/opencode/cron/tasks/<id>.json`

```json
{
  "id": "exemplo-diario",
  "name": "Nome da tarefa",
  "enabled": true,
  "schedule": "0 7 * * *",
  "workdir": "/caminho/pasta/principal",
  "paths": [
    "/caminho/pasta",
    "/caminho/arquivo.ext"
  ],
  "summary": "Resumo curto do que deve ser concluído",
  "prompt": "Descrição completa (prompt) a ser executado pelo OpenCode..."
}
```

Campos:
- `id` (string, obrigatório): identificador único/slug (recomendado igual ao nome do arquivo sem `.json`).
- `name` (string, obrigatório): nome legível da tarefa.
- `enabled` (bool, obrigatório): `true` para ativa, `false` para desativada (não executar).
- `schedule` (string, obrigatório): expressão cron (5 campos) usada no crontab do melchior, ex.: `0 7 * * *`.
- `workdir` (string, recomendado): diretório de trabalho principal da tarefa.
- `paths` (array de strings, recomendado): pastas e/ou arquivos a se trabalhar/considerar.
- `summary` (string, obrigatório): resumo curto do objetivo/entrega.
- `prompt` (string, obrigatório): descrição completa e **prompt a executar** no `opencode run`.
- `self_delete` (bool, opcional): `true` para **apagar a tarefa após executar** (remove o JSON e a linha correspondente do crontab do melchior). Útil para tarefas de uso único.

Opcional (se útil): `model` (`provider/model`), `auto` (bool), `format` (`default`/`json`), `title`.

## Como criar/alterar uma tarefa

1. Criar ou editar `~/.config/opencode/cron/tasks/<id>.json` com o schema acima.
2. Validar o JSON e confirmar `workdir`/`paths` existentes quando aplicável.
3. Agendar no crontab do melchior (ver abaixo). Cada tarefa ativa deve ter sua linha (ou ser chamada por um agendador) respeitando `schedule`.
4. Nunca gravar segredos (senhas, tokens, chaves, `.env`) no JSON nem nos logs.

## Agendamento no crontab do melchior

- Listar: `crontab -l`
- Editar: `crontab -e` (ou instalar de forma controlada com `crontab` a partir de arquivo temporário, preservando entradas existentes).
- Padrão de execução (não interativo, com log):

```cron
# opencode-task:<id>
0 7 * * * /home/melchior/.config/opencode/cron/run-task.sh <id> >> /home/melchior/.config/opencode/cron/logs/<id>.cron.log 2>&1
```

- Use o binário: `/home/melchior/.opencode/bin/opencode` (o runner já referencia).
- O runner lê o JSON em `~/.config/opencode/cron/tasks/<id>.json`, entra em `workdir`, monta o prompt incluindo `summary`/`paths` e executa `opencode run`.
- Para tarefas desacompanhadas normalmente é necessário `--auto`; use com cuidado e escopo bem definido no prompt.
- Ambiente do cron é enxuto: o runner deve garantir `HOME`/`PATH` mínimos.

## Listar e pesquisar tarefas

- Listar: `ls -1 ~/.config/opencode/cron/tasks/*.json`
- Ver todas: `jq -c '{id,name,enabled,schedule,workdir,summary}' ~/.config/opencode/cron/tasks/*.json` (ou `cat`/`python3 -m json.tool` se não houver `jq`).
- Buscar por termo (nome, resumo, prompt, caminho): `grep -Rni "<termo>" ~/.config/opencode/cron/tasks/`
- Ao responder ao Hil sobre tarefas, sempre basear-se nesses arquivos (e no `crontab -l` para o que está efetivamente agendado).

## Guardrails e cuidados

- **Reinício/serviços/containers:** nunca reiniciar, parar ou recriar serviços/containers sem perguntar ao Hil e receber "sim" (ver `AGENTS.md`). Não inclua isso em prompts de tarefas automáticas.
- Não apagar tarefas/entradas de cron sem confirmar com o Hil; prefira `enabled: false` e/ou comentar a linha.
- Teste manualmente antes de agendar: `~/.config/opencode/cron/run-task.sh <id>` (ou `opencode run` equivalente).
- Cada execução é independente; use `--continue/--session` só se a tarefa realmente precisar continuar contexto.

## Exemplo rápido

```json
{
  "id": "checagem-diaria-custo-zero",
  "name": "Checagem diária custo-zero",
  "enabled": true,
  "schedule": "30 8 * * *",
  "workdir": "/data/git/z-one/custo-zero",
  "paths": ["/data/git/z-one/custo-zero/README.md", "/data/git/z-one/custo-zero/automacao"],
  "summary": "Revisar mudanças e pendências do projeto custo-zero",
  "prompt": "Analise o estado atual do repositório em /data/git/z-one/custo-zero, foque em README.md e automacao/, liste mudanças recentes, pendências e próximos passos objetivos. Não altere arquivos nem execute deploy/restart."
}
```

## Notificações (ntfy + sininho no portal)

Toda execução do runner chama `~/.config/opencode/cron/notify.sh` (se existir e for executável), que:

1. grava no SQLite `~/.config/opencode/cron/notifications.db` (fonte da verdade, com `origin` = `usuário@host`);
2. envia push via `ntfy.sh` para o tópico definido em `~/.config/opencode/cron/notify.env` (`NTFY_URL`, `NTFY_TOPIC`, opcional `NTFY_TOKEN`).

- O portal (`https://192.168.2.37/` ou `https://z-server-01.mandrill-court.ts.net/`) mostra um **sininho** no topo com o contador de não lidas; clicar abre o modal. Lido/não lido fica no banco (`read_at`, `read_ip`, `read_ua`), via `POST /api/opencode/notifications/read`.
- Lista exposta em `GET /api/opencode/notifications` (proxy nginx para `opencode-notify-api.service`, `127.0.0.1:9089`).
- **Nunca** grave token do ntfy em git; o `notify.env` fica `600`.

### Cuidado com o `index.html` do portal

`/opt/zlab/nginx/index.html` é montado como **arquivo único** no container `nginx`. Editar **substituindo o inode** (ex.: `install`, `mv`, editor que recria o arquivo) deixa o container servindo a versão antiga. Prefira editar **no lugar** (truncar/reescrever o mesmo arquivo). Se o inode já mudou, recriar o container resolve — e isso exige autorização do Hil (guardrail de reinício).

Se o feed não aparecer no portal, cheque `nginx -t` e a rota `/api/opencode/notifications`.
