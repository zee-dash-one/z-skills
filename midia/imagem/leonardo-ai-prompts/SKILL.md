---
name: leonardo-ai-prompts
description: "Use ao escrever o prompt para o Leonardo.ai: estrutura curta, texto na imagem, negativos, modelo e proporcao."
version: 1.0.0
author: Z Server
license: MIT
metadata:
  hermes:
    tags: [Imagem, Leonardo, Prompt]
---
# Leonardo AI: prompts

## Estrutura (uma frase, em ingles)
`assunto + acao/pose` , `cenario` , `estilo/midia` , `luz` , `composicao/lente` , `cores`. Detalhe visual concreto vale mais que adjetivo vago. Sem nomes de pessoas reais ou artistas vivos.

## Regras
- Texto dentro da imagem: ponha as palavras exatas **entre aspas duplas** no prompt e mantenha curto (ate 3 palavras). Texto longo sai errado: sugira legendar depois.
- "O que evitar": se a tela tiver campo de prompt negativo, use-o (ex.: blurry, extra fingers, watermark). Se nao tiver, diga no proprio prompt o que nao quer.
- Uma ideia por imagem. Para variar, mude 1 elemento por tentativa e anote o que mudou.
- Prompt em pt-BR do Hil: traduza para ingles e devolva o resumo em portugues.

## Modelo (escolha so entre os que aparecem na lista da tela)
- Padrao salvo pedido; sem favorito, **Lucid Origin** para uso geral e imagem nitida; **Phoenix** quando a fidelidade ao prompt (inclusive texto) importar; **FLUX Dev/Schnell** como alternativa rapida.
- Anime, cinematografico, retrato, foto de banco de imagens: use o modelo ou estilo com esse nome, se a lista tiver.
- Modelo que o Hil nomeou: use esse, nao troque.

## Proporcao
Conforme o uso, entre as opcoes da tela: quadrado (post), 9:16 (story/short), 16:9 (capa/YouTube), 4:5 ou 2:3 (retrato). Na duvida, 1:1.

---

Cópia versionada desta skill: [z-skills/midia/imagem/leonardo-ai-prompts/SKILL.md](https://github.com/zee-dash-one/z-skills/blob/main/midia/imagem/leonardo-ai-prompts/SKILL.md). Ao mudar esta skill, atualize também o arquivo no repo.
