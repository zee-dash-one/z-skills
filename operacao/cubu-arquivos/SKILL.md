---
name: cubu-arquivos
description: "Use para guardar, ler, editar ou mostrar arquivos do usuario (relatorios, textos, imagens baixadas, prints) e para enviar imagem ou arquivo no chat."
version: 1.0.0
author: Z Server
license: MIT
metadata:
  hermes:
    tags: [Arquivos, Chat, Imagem]
---
# Arquivos do usuário (ferramenta `cubu_files`)

Pasta própria do usuário. Ações: `list`, `read` (txt, md, csv, json), `write` (texto inteiro), `delete`. Nomes: letras, números, `.`, `-`, `_`, até 3 níveis (`relatorio.md`, `imagens/gato.png`). Binários (imagem, pdf, docx) chegam por download ou print, não por `write`.

## Mostrar no chat
Cole na resposta o campo `show` que a ferramenta devolve:
- imagem: `![descrição](cubu-file:imagens/gato.png)` → o chat mostra a imagem, clique amplia e tem botão **Baixar**
- outro arquivo: `[relatorio.pdf](cubu-file:relatorio.pdf)` → link de baixar
Só funciona com arquivo que existe na pasta (`list` confere). Não escreva caminho do sistema nem URL externa.

## Editar
`read` → altere o texto → `write` com o texto completo. Não apague nada que o usuário não pediu. Nome novo para versão nova só se ele pedir; senão substitua.

## Limites
25 MB por arquivo, 500 MB no total. Cota cheia (`quota_exceeded`): avise e sugira apagar o que não serve mais; não apague sozinho.

---

Cópia versionada desta skill: [z-skills/operacao/cubu-arquivos/SKILL.md](https://github.com/zee-dash-one/z-skills/blob/main/operacao/cubu-arquivos/SKILL.md). Ao mudar esta skill, atualize também o arquivo no repo.
