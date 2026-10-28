# z-skills

Biblioteca de skills do ecossistema de bots do Hil (Z-ONE). Cada pasta tem um `SKILL.md` com a skill completa.

Esta cópia versionada é a referência. Cada skill usada pelos bots aponta para o arquivo correspondente aqui.

## Estrutura

| Categoria | Skill | Para que serve |
|---|---|---|
| `conteudo/escrita` | [artigo-longo-narrativo](conteudo/escrita/artigo-longo-narrativo/SKILL.md) | Use ao escrever, revisar ou reescrever artigos longos para LinkedIn Artigos, Medium e blogs, em português brasileiro ou inglês. Produz em... |
| `conteudo/escrita` | [humanizar-posts-ptbr](conteudo/escrita/humanizar-posts-ptbr/SKILL.md) | Etapa final obrigatória antes de entregar qualquer texto de post de LinkedIn ou Instagram (inclusive legendas): marcar traços de escrita ... |
| `conteudo/escrita` | [prompt-builder](conteudo/escrita/prompt-builder/SKILL.md) | Use when writing, refining or testing a prompt or system prompt for another LLM or agent to use (not media generation). |
| `conteudo/escrita` | [writer-groq-routing](conteudo/escrita/writer-groq-routing/SKILL.md) | Use when writing copy, drafts, titles, threads, or transcripts via Groq, OpenRouter free, or SambaNova (Writer operator or any bot follow... |
| `conteudo/localizacao` | [localizar-ptbr-en](conteudo/localizacao/localizar-ptbr-en/SKILL.md) | Localiza textos de português brasileiro para inglês americano natural, com compreensão obrigatória do contexto global, local e técnico-na... |
| `conteudo/localizacao` | [reforco-localizacao-en](conteudo/localizacao/reforco-localizacao-en/SKILL.md) | Second, mandatory step of every pt-BR to English localization: independent native-English editorial review of a COMPLETED English article... |
| `engenharia` | [estrutura-projeto-agentes](engenharia/estrutura-projeto-agentes/SKILL.md) | Use sempre que for criar, organizar ou orientar tarefas num projeto local para o Cursor ou outro agente de código: garante AGENTS.md na r... |
| `engenharia` | [instrucoes-para-cursor-local](engenharia/instrucoes-para-cursor-local/SKILL.md) | Use sempre que for mostrar, escrever ou executar código, scripts ou comandos de shell para o usuário: em vez de rodar, escreva instruções... |
| `engenharia` | [plan-and-breakdown](engenharia/plan-and-breakdown/SKILL.md) | Use when a feature, fix or technical goal must become a short spec plus ordered, testable tasks (usually .todo/ files for a local Cursor ... |
| `engenharia` | [pr-flow](engenharia/pr-flow/SKILL.md) | Use when the user asks to open, audit, review, merge or release a pull request; includes a short security checklist. |
| `engenharia` | [smoke-test-entrega](engenharia/smoke-test-entrega/SKILL.md) | Use quando o Hil pedir pra verificar uma entrega, disser que uma atualização de um projeto subiu, ou pedir ao PO pra montar ou atualizar ... |
| `midia/audio` | [audio-elevenlabs-tts](midia/audio/audio-elevenlabs-tts/SKILL.md) | Use when generating short narrations (≤3 min) with ElevenLabs TTS via the Áudio operator, including multi-account round-robin across hild... |
| `midia/audio` | [suno-music-jingle](midia/audio/suno-music-jingle/SKILL.md) | Use when a short song or jingle (e.g. for an Instagram post) must be created with the user's signed-in Suno account in the box browser, o... |
| `midia/imagem` | [image-style-presets](midia/imagem/image-style-presets/SKILL.md) | Use when choosing or applying image styles: advertising, anime/manga, realistic, comics/HQ, or kids illustration before generating. |
| `midia/imagem` | [image-visual-routing](midia/imagem/image-visual-routing/SKILL.md) | Use when creating images or game sprites. Only the Image operator generates. Routes SpriteCook, Pika, Leonardo, TensorArt, Krea, or Gener... |
| `midia/imagem` | [leonardo-ai](midia/imagem/leonardo-ai/SKILL.md) | Use when generating still images on Leonardo.ai in the signed-in box browser (app.leonardo.ai). Not for game sprites. |
| `midia/imagem` | [tensorart](midia/imagem/tensorart/SKILL.md) | Use when generating images on TensorArt (tensor.art) via the signed-in box browser. Optional API path if an Access Key is configured late... |
| `midia/video` | [google-ai-studio-veo](midia/video/google-ai-studio-veo/SKILL.md) | Use when generating a short AI video with Veo — prefer Google Flow Veo 3.1 Fast as fallback; AI Studio Veo 3.1 when unlocked. Prefer Imag... |
| `midia/video` | [pixverse-video](midia/video/pixverse-video/SKILL.md) | Use when generating or iterating AI video on PixVerse via the box browser. Prefer image-to-video from an Image-agent still or an uploaded... |
| `midia/video` | [video-shorts-routing](midia/video/video-shorts-routing/SKILL.md) | Use when generating YouTube/IG Shorts (9:16) video clips. Only the Video operator generates. Defaults PixVerse image-to-video; Veo 3.1 on... |
| `operacao` | [ponte-humana](operacao/ponte-humana/SKILL.md) | Use sempre que o Hil pedir algo que outro bot do ecossistema vai executar, incluindo regras ou tarefas novas nos projetos: como a Malfoyd... |
| `projetos/devotio` | [devotio-decisao-reformada](projetos/devotio/devotio-decisao-reformada/SKILL.md) | Use sempre que for decidir ou propor uma funcionalidade, uma permissão ou um papel no Devotio (quem pode o quê, quem lidera, se algo muda... |
| `projetos/devotio` | [devotio-valores-nao-changelog](projetos/devotio/devotio-valores-nao-changelog/SKILL.md) | Use ao escrever conteúdo institucional de um produto (ex.: Instagram e página LinkedIn do Devotio) sobre uma mudança ou funcionalidade no... |

## Regras

- Nada de senhas, chaves ou tokens aqui. Só nomes de variáveis de ambiente (`.env`).
- Mudou uma skill na biblioteca? Atualize o arquivo correspondente aqui no mesmo dia.
