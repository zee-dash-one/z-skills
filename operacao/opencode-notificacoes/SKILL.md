---
name: opencode-notificacoes
description: >-
  Use quando for preciso avisar o Hil de algo muito importante ou registrar que
  uma tarefa de cron foi executada. Ensina o sistema central de notificações do
  OpenCode: SQLite, feed do portal nginx (sininho) e push via ntfy.
---
# Notificações do OpenCode

Sistema único de avisos dos agentes neste servidor. Fonte da verdade em **SQLite**; o portal nginx lê e grava direto no banco via API loopback; o push opcional vai por **ntfy**.

## Quando usar (regra dura)

Use **somente** para:
1. **Aviso muito importante** que exige ação do Hil: falha grave, risco de perda de dados, segurança, serviço fora do ar.
2. **Registro de execução de tarefa cron** — feito automaticamente pelo `run-task.sh`; não duplique manualmente.

Não use para conversa, progresso rotineiro, “terminei”, ou qualquer coisa que já aparece no chat. Se está em dúvida, não notifique.

## Como registrar

```sh
~/.config/opencode/cron/notify-event.sh "<título>" "<mensagem>" important
```

- Grava uma linha em `notifications.db`.
- Regenera o feed do portal.
- Envia push no ntfy (`~/.config/opencode/cron/notify.env`).

O runner de cron chama `~/.config/opencode/cron/notify.sh` sozinho ao final de cada execução; não chame os dois.

## Onde fica

| Peça | Caminho |
|---|---|
| Banco (fonte da verdade) | `~/.config/opencode/cron/notifications.db` |
| API (lê/marca lida) | `opencode-notify-api.service`, `127.0.0.1:9089` |
| Rota no portal | `GET /api/opencode/notifications`, `POST /api/opencode/notifications/read` |
| Config do push | `~/.config/opencode/cron/notify.env` (`600`) |
| Helper de aviso manual | `~/.config/opencode/cron/notify-event.sh` |
| Runner de cron | `~/.config/opencode/cron/run-task.sh` |

Schema da tabela `notifications`: `id, created_at, task_id, name, state, rc, summary, message, log_file, start, end, meta, origin, read_at, read_ip, read_ua`. `state`: `ok`, `erro`, `important`. `origin` é `usuário@host` de quem registrou.

## Consultar

```sh
sqlite3 ~/.config/opencode/cron/notifications.db \
  "select id,created_at,task_id,state,summary from notifications order by id desc limit 20;"
```

Quando o Hil perguntar de notificações, consulte o SQLite e, se precisar do que está no ar, a rota `/api/opencode/notifications`.

## Portal (sininho)

- `https://192.168.2.37/` ou `https://z-server-01.mandrill-court.ts.net/`.
- Contador de não lidas e modal com histórico.
- **Lida/não lida fica no SQLite** (`read_at`, `read_ip`, `read_ua`), não no navegador: sincroniza entre dispositivos. O portal marca ao clicar ou em "Marcar todas como lidas" (`POST /api/opencode/notifications/read`).

## Regras de segurança

- **Nunca** coloque senha, token, chave ou conteúdo de `.env` no título/mensagem.
- O feed é servido pelo portal e o tópico ntfy é público: trate como informação semi-pública.
- O `notify.env` fica `600`; não versione.

## Evolução

O desenho separa **registro** (SQLite) de **entrega** (portal + ntfy). Para adicionar outro canal (e-mail, Telegram, Discord), implemente o envio lendo do SQLite em `notify.sh`; portal e API não mudam. O serviço `opencode-notify-api.service` é stdlib-only e só escuta loopback; o nginx faz o proxy.
