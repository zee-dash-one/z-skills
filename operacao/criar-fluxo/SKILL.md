---
name: criar-fluxo
description: "Use quando o usuario pedir para criar, mudar, listar ou apagar um fluxo de trabalho (receita passo a passo), ou quando uma tarefa se repetir e valer virar fluxo."
version: 1.0.0
author: Z Server
license: MIT
metadata:
  hermes:
    tags: [Fluxo, Workflow]
---
# Criar fluxos de trabalho

Fluxo = receita curta e em ordem para uma tarefa que o usuário repete (gerar imagens, escrever e-mail...). Fica em **Fluxos de trabalho** no menu lateral do app; o usuário liga e desliga. Só fluxo ligado vale.

## Quando criar
- O usuário pede ("crie um fluxo para..."), ou aceita sua ideia depois de a tarefa se repetir. Não crie sozinho em silêncio.
- Antes, veja o que existe (`list`) para não duplicar; para mudar, use `update` com o mesmo título.

## Como escrever (ferramenta de fluxos, ações `create`, `update`, `list`, `delete`)
- **Título** curto e em português simples, para leigos ("Escrever e-mail profissional").
- **Quando usar**: uma frase ("o usuário pedir um e-mail").
- **Passos**: de 2 a 15, cada um uma frase de ação, na ordem real. Pergunte pouco: no máximo 3 perguntas por fluxo. Indique as skills do passo, se houver (`{text, skills:[...]}`).
- Passo que depende do usuário (criar conta, entrar, pagar, confirmar) deve dizer isso e pedir que ele assuma a tela do Computador. Nunca ponha senha, chave ou dado pessoal nos passos.
- Depois de criar, diga em uma frase onde ele aparece e como desligar.

## Seguir um fluxo
Diga em uma frase em que passo está. Não pule passos. Se uma skill do passo não existir, siga com o bom senso e avise.
