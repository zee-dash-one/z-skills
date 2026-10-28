---
name: smoke-test-entrega
description: >-
  Use quando o Hil pedir pra verificar uma entrega, disser que uma atualização
  de um projeto subiu, ou pedir ao PO pra montar ou atualizar o roteiro de smoke
  test do projeto. O PO abre o site publicado e roda o roteiro do README. Só
  roda sob pedido.
---
# Smoke test de entrega (PO do projeto)

## Quando
- Só quando o Hil pedir a verificação, disser que uma atualização subiu, ou quando a Mal repassar esse pedido dele. **Nunca** roda sozinho, nem em rotina, nem a cada deploy.
- Quem roda é o PO dono do projeto. Projeto sem PO próprio (ex.: projetinhos internos da Z-ONE) fica com o PO da Z-ONE.

## Montar ou atualizar o roteiro (sob pedido)
Projeto que ainda não tem a seção `Smoke test` no README não ganha roteiro inventado. Quando o Hil pedir pra montar ou atualizar, o PO participa de todas as etapas:
1. Ler o README, o código e o site publicado pra propor as telas e os fluxos principais.
2. **Decidir sozinho primeiro.** Quando surgir uma dúvida (o que checar, em que ordem, qual resultado esperar), o PO decide com base no site publicado, no README e nas regras do projeto, e registra cada decisão junto da proposta ("Decidi X porque Y").
3. **Escalar ao Hil só o que não dá pra decidir**: conta de teste e credenciais (só no Vault), dados reais de usuários, mudança de escopo do produto, ou falta de informação pra decidir. As perguntas vão juntas, numa mensagem só.
4. Escrever a proposta como lista numerada, com o passo e o resultado esperado, só leitura, mais as decisões registradas.
5. O Hil aprova a versão final.
6. O PO manda a versão aprovada à Mal, que encaminha ao Gandalf, e o Gandalf escreve no README por PR. O merge é do Hil.
7. Depois do merge, o PO confere se o README ficou igual ao roteiro aprovado.

## Rodar o teste
1. **Ler o roteiro.** No repositório oficial, abrir o README e achar a seção `Smoke test` (URL, conta de teste e checagens). Se não existir, avisar o Hil e oferecer montar o roteiro (seção acima).
2. **Saber o que mudou.** Ver o PR ou merge mais recente pra dar atenção extra ao que foi atualizado, além do roteiro fixo.
3. **Abrir o site** no navegador do box. Se a checagem pede login, usar a conta de teste salva no Vault. Senha nunca vai pra README, chat ou arquivo versionado. Se faltar a conta ou cair num 2FA, parar e pedir ao Hil.
4. **Rodar cada checagem** em ordem: navegar, conferir se a tela e o dado aparecem, e tirar screenshot dos passos importantes.
5. **Só ler.** Não criar, editar nem apagar dados reais, a não ser que o roteiro mande explicitamente e use dados de teste.
6. **Relatório ao Hil**, curto: versão ou PR testado, horário (BRT), cada checagem com passou ou falhou, screenshots das falhas e o erro visto.

## Se falhar (ou se o PO vir um erro de deploy)
1. **Alertar o Gandalf na hora**, com o que falhou, os screenshots, o erro e o PR ou deploy suspeito.
2. O Gandalf **sempre** avisa o Hil pelo WhatsApp, por meio do bot WhatsApp, o único que abre o WhatsApp. A mensagem vai assinada pelo Gandalf e explica de forma simples o que aconteceu.
3. **Correção simples**: o PO pode decidir, e o Gandalf refaz o build ou o deploy corretamente. Vale quando não envolve senha, nada inseguro, nem uma decisão que precise do Hil.
4. **Correção que não é simples**: quando envolve senha, segurança, dados reais, escopo ou mudança de código que precisa de merge, o Gandalf só explica e espera o Hil decidir.
5. Mesmo que já esteja resolvido, o Hil é avisado do que aconteceu e do que foi feito.

## Regras
- Só o Gandalf escreve no README ou no repositório. O PO lê e propõe.
- Nada de credencial em texto. Login sempre pelo Vault ou pelo Hil digitando.
- Um relatório por pedido. Sem repetir teste nem monitorar depois.
