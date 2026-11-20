---
name: senhas-no-cofre
description: "Use para entrar em sites com e-mail, usuario, senha ou codigo 2FA do usuario sem ver nem pedir esses valores: caixa de texto no chat, cofre e digitacao direta no campo."
version: 1.0.0
author: Z Server
license: MIT
metadata:
  hermes:
    tags: [Senhas, Login, Cofre]
---
# Senhas no cofre (ferramenta de segredos)

Você **nunca** vê, pede no chat, lê ou guarda e-mail, senha ou código. O usuário digita numa **caixa de texto do chat** que vai direto ao cofre; você só manda digitar no campo da página.

## Fluxo de um login (um campo por vez)
1. Abra a página de login (https) na aba atual.
2. Precisa do valor? Chame a ferramenta de segredos com `request` (`handle` curto como `google-email`, `label` como "E-mail do Google", `kind`). Cole o campo `show` na resposta, diga "digite na caixa acima" e **pare**: quando ele guardar, o chat manda sozinho a mensagem "Guardei ... Pode continuar" (ele não precisa avisar). Siga só depois dela. Se vier `saved: true`, pule este passo.
3. Ao chegar a mensagem de que guardou, **clique no campo** com a ferramenta do navegador e chame `fill` com o `handle`. Só funciona se o site da página for o do segredo e o campo for do tipo certo.
4. Aperte Enter ou clique no botão. Repita para o campo seguinte (ex.: primeiro e-mail, depois senha).

`kind`: `email`, `username`, `password` (só entra em campo de senha), `code` (código de uma vez: some do cofre ao usar, vale 10 min), `text`.

## Regras
- Recusas (`origin_mismatch`, `field_type_mismatch`...) vêm com instrução: siga-a e não insista nem tente outro jeito.
- Você não executa JavaScript nem CDP no navegador (bloqueado); não tente ler o valor do campo.
- Captcha, "confirme no celular" ou bloqueio do site: peça que o usuário assuma a tela do Computador ou aprove no aparelho. Não tente contornar.
- `list` mostra só nome, tipo e site do que ele já guardou. Se faltar algo, use `request`.
- Nunca repita, resuma ou comente um valor, nem o salve na memória ou em arquivo.

---

Cópia versionada desta skill: [z-skills/operacao/senhas-no-cofre/SKILL.md](https://github.com/zee-dash-one/z-skills/blob/main/operacao/senhas-no-cofre/SKILL.md). Ao mudar esta skill, atualize também o arquivo no repo.
