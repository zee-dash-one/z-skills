---
name: leonardo-ai
description: >-
  Use ao gerar imagens no Leonardo.ai (app.leonardo.ai) pelo navegador da box com a conta ja logada. Nao serve para sprites de jogo.
---
# Leonardo AI: operar o site

Pedidos de prompt: skill `leonardo-ai-prompts`. Upscale, fundo, Canvas e custos: `leonardo-ai-edicao-e-tokens`.

## Antes
- Resumo do pedido: assunto, estilo, proporcao, quantidade (padrao **1**), texto na imagem, o que evitar. Sem retrato de pessoa real.
- Gastar token so com pedido claro. Mais de 1 imagem, modelo premium ou varias tentativas: avise o custo e espere o "sim" (a menos que o Hil ja tenha autorizado a rodada).

## Fluxo
1. Use a aba atual: `https://app.leonardo.ai/generate`. Nao abra aba nova.
2. Tela de login ou sessao caiu: use o cofre de senhas; sem senha cadastrada, pare e avise o Hil para entrar pela tela. Nunca peca nem escreva senha.
3. Leia a pagina em **texto** (snapshot), nao em imagem. Ache os controles pelo rotulo que aparece na tela (modelo, proporcao, quantidade, estilo, campo do prompt, botao Generate).
4. Configure um controle por vez: modelo (o padrao, salvo pedido), proporcao, quantidade 1, prompt. Confira no texto da pagina que ficou certo.
5. O custo em tokens aparece no botao de gerar: leia antes de clicar. Se estiver acima do combinado, pare e avise.
6. Gere e espere (de 10 a 60 s). Confira de 5 em 5 s no texto da pagina; sem resultado em 2 min, avise.
7. Entregue: prompt usado, modelo, proporcao, tokens gastos e saldo (visivel no canto inferior esquerdo da home).
8. Arquivo: pegue o endereco direto da imagem gerada (lista de imagens da pagina ou link do botao de baixar) e use `cubu_download` (se tiver). Se recusar, clique no botao de baixar da propria pagina e espere ~10 s: o arquivo cai sozinho na pasta `downloads/` do usuario. Confira com `cubu_files list` e cole o `show` na resposta para o chat exibir a imagem. Sem essas ferramentas, diga que a imagem esta na biblioteca da conta e passe o endereco da pagina.

## Regras
- A tela mudou ou nao acha o controle: pare e descreva o que ve. Nao invente cliques.
- Prompt bloqueado pela moderacao: reescreva uma vez de forma legitima ou avise o Hil. Nunca tente burlar filtro.
- Captcha, verificacao de duas etapas ou aviso de uso suspeito: pare e chame o Hil. Se o Hil assumiu a tela, espere o "terminei".
- Termine com uma aba aberta.

---

Cópia versionada desta skill: [z-skills/midia/imagem/leonardo-ai/SKILL.md](https://github.com/zee-dash-one/z-skills/blob/main/midia/imagem/leonardo-ai/SKILL.md). Ao mudar esta skill, atualize também o arquivo no repo.
