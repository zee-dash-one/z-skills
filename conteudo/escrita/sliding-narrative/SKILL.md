---
name: Sliding Narrative (Akita-style & Degradê)
description: >-
  Metodologia de engenharia de prosa para transições fluidas e narrativas densas,
  adotando o modelo em degradê (A/AB -> B/BC -> C/CD) para evitar deadlocks de atenção
  e garantir vazamento planejado entre temas e capítulos.
---
# Sliding Narrative (PT-BR)

Esta skill governa a **Engenharia de Fluxo** da escrita técnica e narrativa densa. O texto é tratado como um pipeline contínuo de execução, onde não existem interrupções abruptas nem "deadlocks" de atenção.

---

## 1. O Modelo em Degradê: Por que abandonar blocos (A - B - C) para usar A/AB -> B/BC -> C/CD?

Na escrita densa (inspirada no conceito do **"Tobogã" de Joseph Sugarman** e no ritmo de autoridade técnica contínua estilo Akita), a transição em blocos estanques cria **"ilhas" de pensamento**. 

Quando um parágrafo começa e termina rigidamente no mesmo tema (A), a passagem para o próximo tema (B) exige um salto cognitivo do leitor. Esse atrito quebra a imersão e drena a autoridade técnica do fluxo.

### O Vazamento Planejado (*Leaky Abstraction* Narrativa)
No modelo em degradê:
- O parágrafo/bloco começa focado na tese atual (**A**).
- No seu terço final, introduz de forma inevitável e orgânica uma semente ou consequência direta do próximo ponto (**AB**).
- O parágrafo seguinte já nasce aterrissado nessa consequência (**B**), desenvolve seu núcleo e encerra transbordando para o próximo elo (**BC**).

O leitor não percebe que mudou de assunto, pois simplesmente desliza pela consequência causal.

### Exemplo Prático de Encadeamento Causal
A engenharia da prosa atua para transformar temas complexos em um vetor ininterrupto:
1. **A -> AB:** A ansiedade individual do consumidor diante da inflação transborda para o esvaziamento da prateleira do mercado.
2. **B -> BC:** A prateleira vazia expõe a fragilidade da logística de distribuição *just-in-time*.
3. **C -> CD:** A logística falha atrai a especulação e a exploração de preços por intermediários.
4. **D -> DE:** A exploração evidente exige uma retomada racional e metódica do controle doméstico.

---

## 2. Aplicação em Nível Micro (Parágrafos e Frases)

Cada parágrafo funciona como um *commit* atômico que prepara o ambiente de compilação para o seguinte:

- **Entrada (Tema A):** Estabelece o argumento ou fato técnico de forma direta e sem rodeios.
- **Corpo:** Adiciona densidade, dados de causa-raiz ("under the hood") ou analogias mundanas de alto impacto.
- **Transbordamento (AB):** Lança o gancho causal inevitável.
- **Conectores de Continuidade:** Banir conectores genéricos ("Além disso", "Por outro lado", "Ademais"). Usar conectores causais e de infraestrutura:
  - *"O efeito colateral imediato desse arranjo é..."*
  - *"Essa assimetria não fica restrita ao código: ela bate na ponta física quando..."*
  - *"O sintoma visível é o preço na gôndola, mas a engrenagem que quebrou antes foi..."*

---

## 3. Aplicação em Nível Macro (Entre Capítulos)

A mesma lógica em degradê deve ser aplicada entre os grandes blocos de pensamento da obra:
- **Fechamento do Capítulo N:** O parágrafo final do Capítulo N conclui a sua tese interna, mas deixa aberta a pergunta operacional ou o desdobramento crítico que o Capítulo N+1 é obrigado a responder.
- **Abertura do Capítulo N+1:** Não começa do zero nem faz recapitulações mornas. Ele engata diretamente no resíduo deixado pelo Capítulo N e acelera o novo tema.

---

## 4. Protocolos de Verificação e Revisão

### A. Análise de Coesão do Capítulo
Durante a escrita e obrigatoriamente na revisão, audite cada bloco de parágrafos:
- Existe algum parágrafo que é uma "ilha" (começa e fecha em si mesmo sem tocar no seguinte)?
- O vazamento AB para B é natural ou parece uma emenda colada à força?

### B. Análise de Integração entre Capítulos
Para cada transição de capítulos (Capítulo N -> Capítulo N+1), responder e registrar:
1. **Sentido N -> N+1:** O final do capítulo N tem sentido direto com o início do capítulo N+1?
2. **Desfecho Interno:** O final do capítulo N oferece um desfecho coerente com o desenvolvimento interno do próprio capítulo?
3. **Coerência de Entrada:** O início do capítulo N+1 faz sentido com a progressão do texto que virá a seguir?
4. **Resonância de Grafo:** A transição honra ao menos uma ligação forte ou fraca mapeada no livro?

*Se qualquer resposta for "não", reescrever cirurgicamente o término de N e o início de N+1.*

### C. Análise de Page-Turner (Eliminação de Zonas Mortas)
Auditar o ritmo de leitura para garantir tração contínua:
1. **Identificar os 3 Piores Pontos:** Localizar trechos onde a leitura desacelera, o tom fica excessivamente expositivo/acadêmico ou há perda de tensão e curiosidade.
2. **Reescrita Cirúrgica em Degradê:** Aplicar o modelo A/AB -> B/BC reescrevendo o texto **diretamente anterior** e **diretamente posterior** aos 3 piores pontos identificados, reinjetando atrito e deslizamento irresistível.

---

## 5. Densidade Técnica e Autoridade
- **Eliminação de Adjetivos Ocos:** Trocar adjetivos ("muito arriscado", "extremamente volátil") por causas sistêmicas, métricas reais, latência de reposição e incentivos de mercado.
- **Voz de Engenharia Realista:** Falar com o ceticismo de quem conhece os bastidores da máquina e não tem paciência para ilusões superficiais.

---
**Regra de Ouro:** A escrita não é uma troca de temas, é um deslizamento técnico contínuo. Se o leitor percebeu o corte de assunto, a abstração falhou. A transição deve ser tão suave quanto uma mudança de cor num degradê e tão inevitável quanto a gravidade num tobogã.
---

Cópia versionada desta skill: [z-skills/conteudo/escrita/sliding-narrative/SKILL.md](https://github.com/zee-dash-one/z-skills/blob/main/conteudo/escrita/sliding-narrative/SKILL.md). Ao mudar esta skill, atualize também o arquivo no repo.
