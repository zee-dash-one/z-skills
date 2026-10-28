---
name: Suno Music Jingle
description: >-
  Use when a short song or jingle (e.g. for an Instagram post) must be created
  with the user's signed-in Suno account in the box browser, or when downloading
  a generated Suno track as MP3.
---
# Suno — música / jingle curto

Use quando precisar criar música ou jingle (ex.: post curto de Instagram) na conta Suno do usuário, pelo navegador da box. O Suno não tem conector; o login fica salvo no navegador.

## Montar o prompt
Sempre inclua, em português brasileiro (a menos que peçam outro idioma):
1. **Emoção** (ex.: alegre, nostálgico, épico)
2. **Estilo/gênero** (pode misturar: ex.: jazz + pop)
3. **Tema** (sobre o quê é a música)
4. **Duração** (posts curtos: ~30 s a 1 min)
5. **Um ou dois detalhes marcantes** (ex.: vocal feminino marcante, rasgado mas suave; refrão catchy)
6. **Idioma** do vocal

Exemplo de referência:
> Quero um jingle curto de 1 minuto, alegre, com vocal marcante feminino, rasgado mas suave. Música jazz misturada com pop, sobre a alegria de ter amigos, em português brasileiro. Refrão catchy.

## Gerar (navegador da box, via subagente de computador)
1. Abrir https://suno.com/create (aba Songs).
2. Se não estiver logado, parar e pedir ao usuário que entre (handoff da tela). Nunca criar conta.
3. Modo Simple: colar o prompt completo na descrição da música. Modo Advanced: letra em Lyrics (ou vazio pra instrumental) e estilo/gênero/detalhes em Styles.
4. Clicar Create uma vez só (cada geração gasta créditos; o Suno costuma devolver 2 versões).
5. Esperar as faixas terminarem e anotar título, duração e link de cada uma (botão Share / link da música, formato `https://suno.com/song/<id>`).
6. Não publicar, não tornar público e não compartilhar fora sem pedido explícito.

## Baixar MP3
Quando precisar do arquivo (entrega local, Video, etc.):
1. Abrir https://usesuno.com/pt-br/tools/downloader/ — **não precisa de login**.
2. Colar a URL da música gerada (`https://suno.com/song/<id>`) no campo textarea com `id="dl-input"`.
3. Baixar como **Audio** e **MP3**.
4. Salvar o arquivo em `/workspace/audio/` (ou caminho combinado) e anotar o path absoluto.
5. Se qualquer passo do usesuno falhar (site fora, download quebrado, formato errado), baixar direto do Suno na página da faixa e avisar o usuário.

## Entregar
- Título, duração e link de cada versão.
- Path do MP3 no box, quando o download foi feito.
- O prompt usado.
- Créditos restantes, se aparecerem na tela.
- Se os créditos acabarem ou o plano gratuito bloquear algo, avisar o usuário em vez de tentar contornar.
