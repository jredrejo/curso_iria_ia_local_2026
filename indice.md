1. Por qué usar local (motivación)
  Por qué local: privacidad, soberanía, coste, y el "ya es viable"
In the last 20 years of GPU development, compute capacity has grown roughly 60,000x. Memory bandwidth? Only about 100x. Read that again. There's a 600x


2. Contexto: de dónde venimos (evolución 2022-2026, no solo 6 meses)
3. Qué es un LLM (definición accesible, tipos de modelos)
 Qué es un LLM: definición simple, cómo funciona, formatos (MOE,GGUF, etc.)
4. Opciones de hardware (qué necesitas para correr local)
 desde una Raspberry Pi hasta una GPU de sobremesa
5. Inferencia local: herramientas (llama.cpp, vllm, LM Studio)
5.1 llama.cpp
5.2 ollama (koboldcpp)
5.3 lmstudio
5.4 krasis https://github.com/brontoguana/krasis

6. Servir modelos en producción:
   vLLM, AnythingLLM

7. Sección: RAG: qué es, por qué importa. Demo


8.  Agentes de código → "La IA escribe código por mí"  

9. Sección: Agentes, Skills, MCP, Loops: nomenclatura que da poder

10 Sección: Montar tu propio asistente: paso a paso, de cero . OpenClaw, Hermes

11. Más allá de los LLM: Pinokio, IA en dispositivos pequeños, Memoria Karpathy 

12 Sección: Conclusión: lo que SÍ puedes hacer localmente hoy

13. Apéndice


1.
https://wwwhatsnew.com/2026/06/20/prem-ai-serie-a-100-millones-ia-soberana-bancos-bufetes-2026/
https://app.supermo.no/share/032e524fc0758c2a/feafb5d7af
https://news.ycombinator.com/item?id=48555993
https://fortune.com/2026/05/22/microsoft-ai-cost-problem-tokens-agents/
https://x.com/HedgieMarkets/status/2057250823088771499
https://llm-stats.com/benchmarks/swe-bench-verified


2.
https://simonwillison.net/2026/May/19/5-minute-llms/
https://x.com/victormustar/status/2063017894221591008
https://freedium-mirror.cfd/https://levelup.gitconnected.com/glm-5-2-beats-gpt-5-5-on-coding-at-1-6-the-cost-3b228a78de07
https://archive.ph/4dBUB


3.
https://models.dev/
https://platform.openai.com/tokenizer
https://rightmodel.dev/ 
https://x.com/rasbt/status/2062235700636873082/photo/1
https://x.com/MiaAI_lab/status/2067612609294008558
https://x.com/nullfoundry/status/2067605713694691745
https://github.com/cheahjs/free-llm-api-resources
https://www.cerebras.ai/pricing
https://artificialanalysis.ai/models
-- benchmarks para modelos:
  https://github.com/lechmazur/buyout_game
  https://github.com/lechmazur/pact/ 
  https://github.com/lechmazur/nyt-connections/
  https://github.com/lechmazur/debate

4. 
https://archive.ph/DkXQx
https://archive.ph/QgkFQ
https://freedium-mirror.cfd/https://ai.gopubby.com/gemma-4-on-old-gpus-why-a-700-used-card-beats-20-000-of-professional-hardware-ba81680a2fc4#the-hardware
https://blog.elhacker.net/2025/02/nvidia-tesla-p40-ia-ollama-llm.html
https://freedium-mirror.cfd/https://medium.com/@paulhoke/the-complete-guide-to-running-large-language-models-locally-in-2026-hardware-tools-and-da9efb3170be
https://freedium-mirror.cfd/https://agentnativedev.medium.com/m5-macbook-pro-or-nvidia-dgx-spark-or-rtx-pro-6000-47480de9ec3a
https://terminalbytes.com/best-mini-pc-for-local-llm-2026/
https://freedium-mirror.cfd/https://julsimon.medium.com/what-to-buy-for-local-llms-april-2026-a4946a381a6a

5.
https://github.com/Alishahryar1/free-claude-code
https://touchdown-labs.com/blog/kv-cache-memory-hierarchy-inference.html
https://freedium-mirror.cfd/https://pub.towardsai.net/7-local-llm-families-to-replace-gpt-5-4-codex-for-everyday-tasks-37e8000bd751
https://freedium-mirror.cfd/https://medium.com/coding-nexus/i-ran-googles-gemma-4-26b-moe-autonomous-agent-on-an-8gb-vram-laptop-39e6559bd3eb
https://x.com/TraffAlex/status/2066236717015728227
https://huggingface.co/JetBrains/Mellum2-12B-A2.5B-Instruct
https://freedium-mirror.cfd/https://medium.com/artificial-intel-ligence-playground/jetbrains-mellum2-is-the-best-low-resources-local-coding-agent-llm-e7ead8d02b4e
https://huggingface.co/unsloth/diffusiongemma-26B-A4B-it-GGUF
https://huggingface.co/WeiboAI/VibeThinker-3B
https://freedium-mirror.cfd/https://medium.com/data-science-collective/12b-might-be-the-new-sweet-spot-for-local-ai-ca33b22f0634

5.1
https://carteakey.dev/blog/local-inference/local-llm-optimization/
https://freedium-mirror.cfd/https://piedpay.medium.com/running-a-35b-large-model-local-ai-agent-on-6gb-vram-the-complete-deployment-guide-for-qwen3-6-35-7513982c19c3
https://github.com/lostruins/koboldcpp 
- Compilar llama.cpp
  1.
    rm -Rf build
  2.-
  "cambiar variable DCMAKE_CUDA_COMPILER dependiendo de versión de cuda instalada"
  cmake -B build \
  -DGGML_CUDA=ON \
  -DCMAKE_CUDA_COMPILER=/usr/local/cuda-13.3/bin/nvcc \
  -DCMAKE_CUDA_ARCHITECTURES=native \
  -DCMAKE_BUILD_TYPE=Release \
  -DLLAMA_BUILD_TESTS=OFF \
  -DLLAMA_BUILD_EXAMPLES=OFF \
  -DGGML_CUDA_FA_ALL_QUANTS=ON \
  -DGGML_NATIVE=ON 
  3.- 
    cmake --build build --config Release -j$(nproc)

6.
https://freedium-mirror.cfd/https://medium.com/startup-insider-edge/running-private-ai-locally-ollama-lm-studio-anythingllm-2026-guide-9b4659955419

7.
https://freedium-mirror.cfd/https://ai.gopubby.com/rag-llm-wiki-or-gbrain-how-your-agent-remembers-changes-everything-56829e66725c


8.
https://github.com/open-gsd/gsd-core
https://github.com/obra/Superpowers
https://x.com/filicroval/status/2052753382079651864 

9
https://addyosmani.com/blog/agent-skills/
https://archive.ph/RDMCf
https://www.ui-skills.com/
https://www.skills.sh/
https://huggingface.co/learn/agents-course/en/unit0/introduction
https://notes.ansonbiggs.com/youre-probably-using-agent-skills-wrong/
https://x.com/akshay_pachaar/status/2069404367497953592
https://modelcontextprotocol.io/docs/getting-started/intro
https://walkinglabs.github.io/learn-harness-engineering/en/
https://developer.chrome.com/docs/modern-web-guidance?hl=es-419


10
https://freedium-mirror.cfd/https://ai.gopubby.com/rag-llm-wiki-or-gbrain-how-your-agent-remembers-changes-everything-56829e66725c
https://x.com/shannholmberg/status/2055335043904492011
https://x.com/akshay_pachaar/status/2054564519280804028
https://freedium-mirror.cfd/@creativeaininja/hermes-agent-the-open-source-ai-agent-that-actually-remembers-what-it-learned-yesterday-278441cd1870
https://freedium-mirror.cfd/https://www.towardsdeeplearning.com/hermes-agent-the-hype-the-reality-and-who-should-actually-use-it-acc20bc94d32
https://freedium-mirror.cfd/https://medium.com/data-science-collective/what-is-hermes-agent-and-why-its-better-than-openclaw-for-personal-ai-workflows-d59d83436ad2
https://freedium-mirror.cfd/https://pub.towardsai.net/a-beginner-friendly-guide-to-running-openclaw-for-free-04459be33ca0


11
https://github.com/ferdous-alam/GenCAD
- solo uno de éstos:
  -- https://freedium-mirror.cfd/https://medium.com/neuralnotions/andrej-karpathy-stopped-using-ai-to-write-code-hes-using-it-to-build-a-second-brain-instead-cddceadc5df5
  -- https://freedium-mirror.cfd/https://medium.com/@roanmonteiro/building-a-complete-personal-harness-llm-wiki-developers-second-brain-in-obsidian-d7b61c7398ff
  -- https://freedium-mirror.cfd/https://medium.com/graph-praxis/your-obsidian-vault-is-a-knowledge-graph-heres-how-to-make-it-think-quickly-1487614a7682


13.
https://x.com/chesny/status/2068396516016824803
https://freedium-mirror.cfd/https://medium.com/lets-code-future/20-most-important-ai-concepts-explained-in-just-20-minute-b7dd3ad2b506
https://gs-run.github.io/prompt-engineering-course/index.html
