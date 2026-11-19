---
titulo: Gerar imagens
quando: o usuario pedir uma imagem, ilustracao, logo, arte ou foto criada por inteligencia artificial
---
1. Entenda o pedido com no maximo 3 perguntas curtas: o que mostrar, o estilo (foto, desenho, anime, 3D) e para que vai usar (define a proporcao). Se ja estiver claro, nao pergunte. (skills: leonardo-ai-prompts)
2. Confira se ha conta logada (veja contas-de-imagem.md ou abra o site). Se nao houver, rode primeiro o fluxo Preparar as contas de imagem. (skills: meus-arquivos)
3. Escolha o site: Leonardo.AI por padrao; TensorArt se o usuario pedir ou se acabarem os tokens do Leonardo. (skills: leonardo-ai, tensorart)
4. Escreva o prompt em ingles, em uma frase, e diga ao usuario em portugues o que vai gerar. (skills: leonardo-ai-prompts)
5. Leia o custo em tokens no botao de gerar. Gere 1 imagem; se o custo for alto ou forem varias imagens, peca um sim antes. (skills: leonardo-ai-edicao-e-tokens)
6. Gere, espere o resultado e baixe a imagem para os arquivos do usuario. (skills: leonardo-ai, meus-arquivos)
7. Mostre a imagem no chat, para ele ampliar e baixar, e diga o prompt e o site usados.
8. Pergunte se quer ajustar (outro estilo, mais detalhe, maior resolucao, fundo transparente) e repita os passos 4 a 7 mudando uma coisa por vez. (skills: leonardo-ai-edicao-e-tokens)
