# Presentación — Workshop «Monta tu IA Local»

> Ponente: **José L. Redrejo Rodríguez** · IRIA, Almendralejo · 25 de junio de 2026
> https://iriavr.es/actividades/workshop-monta-tu-ia-local
>
> Guion de diapositivas. Cada diapositiva incluye: **Título**, **Contenido**, **Enlaces** e **Imágenes** (con URL).
>
> **Imágenes locales** (en esta carpeta):
> - `estadistica_programacion.png` — gráfico de estadísticas 2026.
> - `imagenes/capturas/*.png` — capturas limpias de apps (Ollama, LM Studio, VS Code) extraídas para el taller.
> - `imagenes/logos/*` y `imagenes/diagramas/*` — logos oficiales y diagramas propios.
>
> **Nota:** las imágenes marcadas como *(diagrama a crear)* no tienen un asset oficial; junto a ellas se deja la URL de referencia visual o la fuente del gráfico.

---
## PREVIA
- Contraseña para entrar en los ordenadores del curso:  Pass_temp_0805
- IP Servidor IRIA: http://10.10.10.62:8000/v1


## SECCIÓN 1 — Por qué usar IA local (motivación)

### Diapositiva 1.1 — Portada de sección
- **Título:** ¿Por qué ejecutar IA en tu propio ordenador?
- **Contenido:**
  - Privacidad · Soberanía · Coste · "Ya es viable"
  - La IA local pasó de experimento a herramienta diaria.
- **Imágenes:**
  - *(portada del taller; sin imagen de marca externa)*

### Diapositiva 1.2 — El dato que lo cambia todo (2026)
- **Título:** La IA ya está en el día a día del desarrollo
- **Contenido (gráfico de 3 cifras):**
  - **84 %** de developers usa IA para programar en su día a día.
  - **41 %** del código se genera con IA.
  - **36 %** de confianza en los resultados producidos sin supervisión.
  - *Fuente: informes de Google, Microsoft, GitHub y Stack Overflow.*
- **Imágenes:**
  - `estadistica_programacion.png`

### Diapositiva 1.3 — Las 3 ventajas que lo cambian todo
- **Título:** Privacidad, coste cero y modo offline
- **Contenido:**
  - **Privacidad absoluta:** tu código nunca sale de tu ordenador. Única forma 100 % segura para datos bajo NDA o de clientes.
  - **Cero costes extra:** sin cuota mensual de tokens ni caídas de API. Es gratis.
  - **Modo offline:** funciona sin conexión; tu copiloto siempre listo.
  - El problema con la nube: "usar IA en la nube = enviar tus datos, tu lógica de negocio y tu código a los servidores de otra empresa".
- **Imágenes:**
  - *(diapositiva de texto; sin imagen)*

### Diapositiva 1.4 — El cuello de botella del hardware (por qué AHORA es viable)
- **Título:** 60.000× cómputo vs. 100× ancho de banda → la brecha de 600×
- **Contenido:**
  - En los últimos 20 años de desarrollo de GPUs, la capacidad de **cómputo creció ~60.000×**.
  - El **ancho de banda de memoria solo ~100×**.
  - Resultado: una **brecha de 600×** → la inferencia local está limitada por *memoria*, no por cómputo. De ahí la importancia de la cuantización, MoE y la VRAM.
  - Idea fuerza: el hardware de consumo y los modelos pequeños han alcanzado el punto en que correr local "ya merece la pena".
- **Imágenes:**
  - `imagenes/diagramas/1-4-brecha-hardware.svg`
- **Enlaces:**
  - Coste de tokens / agentes (Fortune): https://fortune.com/2026/05/22/microsoft-ai-cost-problem-tokens-agents/
  - IA soberana — Prem AI Serie A 100M: https://wwwhatsnew.com/2026/06/20/prem-ai-serie-a-100-millones-ia-soberana-bancos-bufetes-2026/
  - SWE-bench Verified (ranking de modelos): https://llm-stats.com/benchmarks/swe-bench-verified
  - Discusión HN: https://news.ycombinator.com/item?id=48555993
  - Estadísticas de uso de IA en desarrollo (Supermo): https://app.supermo.no/share/032e524fc0758c2a/feafb5d7af
  - El coste real de la IA en la nube: https://x.com/HedgieMarkets/status/2057250823088771499

---

## SECCIÓN 2 — Contexto: de dónde venimos (2022 → 2026)

### Diapositiva 2.1 — No son 6 meses, son 4 años
- **Título:** De ChatGPT (2022) a la IA local madura (2026)
- **Contenido:**
  - 2022 — ChatGPT populariza los LLM.
  - 2023-2024 — Llama abre la puerta a los modelos open-weight; nace el ecosistema local (llama.cpp, GGUF, cuantización).
  - 2025 — Los **agentes de código** cruzan el umbral de calidad (RLVR). Pasan de experimento a "daily driver".
  - 2026 — Modelos abiertos potentes y pequeños corren en hardware de consumo.
- **Imágenes:**
  - `imagenes/diagramas/2-1-timeline.svg`

### Diapositiva 2.2 — El punto de inflexión (finales de 2025)
- **Título:** El liderazgo cambió de manos 5 veces en un mes
- **Contenido:**
  - Nov 2025: GPT-5.1 → Gemini 3 → GPT-5.1 Codex Max → Claude Opus 4.5 (liderazgo intercambiado 5 veces).
  - "Reinforcement Learning from Verifiable Rewards" (RLVR) hizo que los agentes "mostly-work" como herramienta diaria.
  - Abril 2026: **Gemma 4** (mejores pesos abiertos de una empresa de EE. UU.) y **GLM-5.1** (754B, 1,51 TB open-weight).
  - **Qwen3.6-35B-A3B** rinde en hardware de consumo (~20,9 GB).
  - Mayo 2026: **Gemma 4 12b**: multimodal en tamaño de equipos de consumo
  - Junio 2026:  **GLM-5.2** al a altura de GPT 5.5 y Opus 4.5. Disponible para descarga.
- **Imágenes:**
  - Icono Qwen: imagenes/logos/qwen.png
- **Enlaces:**
  - Simon Willison — "LLMs en 5 minutos" (timeline): https://simonwillison.net/2026/May/19/5-minute-llms/
  - GLM-5.2 supera a GPT-5.5 en coding a 1/6 del coste: https://freedium-mirror.cfd/https://levelup.gitconnected.com/glm-5-2-beats-gpt-5-5-on-coding-at-1-6-the-cost-3b228a78de07
  - Víctor Mustar (estado open models): https://x.com/victormustar/status/2063017894221591008

### Diapositiva 2.3 — La tendencia: abierto, barato y local
- **Título:** Los modelos abiertos cierran la brecha (y a menor coste)
- **Contenido:**
  - Modelos chinos y abiertos (DeepSeek, GLM, Qwen) compiten con los cerrados.
  - Mismo nivel de coding a una fracción del coste (ej. GLM ≈ 1/6 del coste).
  - Implicación: lo que antes exigía la nube, hoy cabe en tu máquina.
- **Imágenes:**
  - Icono DeepSeek: imagenes/logos/deepseek.png
- **Enlaces:**
  - Archivo de referencia: https://archive.ph/4dBUB

---

## SECCIÓN 3 — Qué es un LLM

### Diapositiva 3.1 — Definición accesible
- **Título:** ¿Qué es un LLM? Un autocompletado gigante
- **Contenido:**
  - Un **Large Language Model** predice el siguiente *token* (trozo de palabra) a partir del texto anterior.
  - Entrenado con enormes cantidades de texto; "aprende" patrones del lenguaje.
  - No "razona" como un humano: calcula probabilidades. Pero a gran escala, emergen capacidades (resumir, programar, traducir).
  - Conceptos clave: **tokens**, **contexto** (memoria de la conversación), **parámetros** (tamaño del modelo: 3B, 8B, 70B…).
- **Imágenes:**
  - *(captura a tomar del tokenizer en vivo)* — fuente: https://platform.openai.com/tokenizer

### Diapositiva 3.2 — Tipos de modelos (comparativa)
- **Título:** Abiertos vs. cerrados: el panorama 2026
- **Contenido (tabla — fuente models.dev):**

  | Modelo | Proveedor | Contexto | Precio (in/out) | Acceso |
  |---|---|---|---|---|
  | GPT-5.5 | OpenAI | 1.05M | $3.00 / $18.00 | Cerrado |
  | Claude Opus 4.8 | Anthropic | 1M | $4.29 / $21.46 | Cerrado |
  | Gemini 2.5 Pro | Google | 1.04M | $0.87 / $7.00 | Cerrado |
  | DeepSeek V4 Pro | DeepSeek | 1M | Gratis | **Abierto** |
  | Mistral Large 3 | Mistral | 262K | $0.50 / $1.50 | **Abierto** |
  | Qwen3.7 Max | Alibaba | 1M | Gratis | Cerrado |

- **Enlaces:**
  - Base de datos comparativa de modelos: https://models.dev/
  - Análisis y benchmarks: https://artificialanalysis.ai/models
  - Elegir el modelo adecuado: https://rightmodel.dev/
  - APIs gratuitas de LLM: https://github.com/cheahjs/free-llm-api-resources
  - Inferencia ultrarrápida (precios): https://www.cerebras.ai/pricing
  - Comparativa visual de modelos: https://x.com/rasbt/status/2062235700636873082
  - MiaAI Lab — comparativa de modelos: https://x.com/MiaAI_lab/status/2067612609294008558
  - Nullfoundry — benchmarks: https://x.com/nullfoundry/status/2067605713694691745

### Diapositiva 3.3 — Formatos y arquitecturas: GGUF, MoE, cuantización
- **Título:** GGUF, MoE y cuantización: por qué cabe en tu PC
- **Contenido:**
  - **GGUF:** formato de archivo único y portable usado por llama.cpp / Ollama / LM Studio. Empaqueta pesos + metadatos.
  - **Cuantización (Q4, Q5, Q8…):** comprime los pesos (de 16 bits a 4-8 bits). Pesa mucho menos (4-8 GB) y casi no pierde calidad. *Truco: elige versiones que acaban en `Q4_K_M`.*
  - **MoE (Mixture of Experts):** solo activa una parte de los parámetros por token (ej. 35B con solo 3B activos → "A3B"). Rinde como uno grande consumiendo como uno pequeño.
  - **Dense vs. MoE:** dense usa todos los parámetros; MoE activa "expertos" → más eficiente en local.
- **Imágenes:**
  - Captura de LM Studio mostrando `Q4_K_M`: `imagenes/capturas/p8-000.png`
  - `imagenes/diagramas/3-3-moe.svg`
- **Enlaces:**
  - Sweet spot 12B para IA local: https://freedium-mirror.cfd/https://medium.com/data-science-collective/12b-might-be-the-new-sweet-spot-for-local-ai-ca33b22f0634
  - Gemma 4 26B MoE en laptop de 8 GB VRAM: https://freedium-mirror.cfd/https://medium.com/coding-nexus/i-ran-googles-gemma-4-26b-moe-autonomous-agent-on-an-8gb-vram-laptop-39e6559bd3eb
  - Benchmarks de razonamiento de modelos:
    - Buyout game: https://github.com/lechmazur/buyout_game
    - NYT Connections: https://github.com/lechmazur/nyt-connections/
    - Debate: https://github.com/lechmazur/debate

---

## SECCIÓN 4 — Opciones de hardware (qué necesitas para correr local)

> Enlaces de referencia:
> - Hardware recomendado para LLMs locales: https://archive.ph/DkXQx
> - Comparativa de GPUs para IA: https://archive.ph/QgkFQ

### Diapositiva 4.1 — De una Raspberry Pi a una GPU de sobremesa
- **Título:** No necesitas el ordenador de la NASA
- **Contenido:**
  - El factor limitante es la **memoria** (VRAM/RAM unificada) y su **ancho de banda**, no la potencia de cómputo.
  - Regla rápida:
    - **8 GB RAM** → modelos pequeños (3B-8B cuantizados).
    - **16 GB RAM** → "vas sobrado" para modelos decentes.
    - **GPU dedicada (NVIDIA/AMD) o Mac M1/M2/M3** → vuela.
  - Almacenamiento: cada modelo pesa entre **2 y 20 GB**.
  - Truco: LM Studio te avisa (colores) si el modelo cabe en tu memoria antes de descargarlo.
- **Imágenes:**
  - Captura LM Studio con indicador de memoria: `imagenes/capturas/p8-000.png`
  - Icono Raspberry Pi: imagenes/logos/raspberrypi.svg

### Diapositiva 4.2 — Mini PCs para IA local (comparativa 2026)
- **Título:** Mini PCs: el "sweet spot" para empezar
- **Contenido (tabla — fuente terminalbytes):**

  | Modelo | RAM | Ancho banda | Precio | Notas |
  |---|---|---|---|---|
  | GMKtec EVO-X2 (Ryzen AI MAX+ 395) | 96-128 GB | 256 GB/s | $2.349-3.299 | Corre modelos 70B |
  | Beelink SER10 MAX | 32 GB DDR5 | 86 TOPS | $1.799 | "Sweet spot" dev, 27B Q4 |
  | Beelink SER9 | 32 GB LPDDR5 | iGPU 780M | $859 | Modelos 7B-13B |
  | origimagic A3 | 32 GB DDR5 | — | $609 | El más asequible |
  | Mac Studio M4 Max | 128 GB | 546 GB/s | $3.699 | 70B, software maduro |
  | DGX Spark | 128 GB | 273 GB/s | $4.699 | Ecosistema NVIDIA |

- **Imágenes:**
  - *(foto de producto opcional; sin asset oficial libre)* — fuente: https://terminalbytes.com/best-mini-pc-for-local-llm-2026/
- **Enlaces:**
  - Comparativa mini PCs 2026: https://terminalbytes.com/best-mini-pc-for-local-llm-2026/

### Diapositiva 4.3 — GPUs y Macs: inferencia vs. entrenamiento
- **Título:** ¿Qué comprar? El ancho de banda manda
- **Contenido (tabla — fuente Julien Simon, abr. 2026):**

  | Hardware | VRAM | Ancho banda | Precio | Ideal para |
  |---|---|---|---|---|
  | RTX 5090 | 32 GB | 1.792 GB/s | $5-8K (equipo) | <30B, 60-90 tok/s |
  | Mac Studio M4 Max | 128 GB | 546 GB/s | $3.699 | 70B, 8-15 tok/s |
  | RTX PRO 6000 | 96 GB | 1.8 TB/s | $22K | 70B + varios usuarios |
  | AMD Strix Halo | 128 GB | 212 GB/s | $2.000 | Económico, MoE |

  - **Claves:** en inferencia manda el ancho de banda → Apple Silicon ofrece el mejor precio/ancho de banda. Para entrenar (QLoRA) la RTX 5090 va bien en local; para modelos grandes, nube (B200).
- **Imágenes:**
  - `imagenes/diagramas/4-3-ancho-banda.svg`
- **Enlaces:**
  - Qué comprar para LLMs locales (abr. 2026): https://freedium-mirror.cfd/https://julsimon.medium.com/what-to-buy-for-local-llms-april-2026-a4946a381a6a
  - Gemma 4 en GPUs viejas — tarjeta usada de $700 vence a $20.000 pro: https://freedium-mirror.cfd/https://ai.gopubby.com/gemma-4-on-old-gpus-why-a-700-used-card-beats-20-000-of-professional-hardware-ba81680a2fc4
  - NVIDIA Tesla P40 para IA/Ollama (low cost): https://blog.elhacker.net/2025/02/nvidia-tesla-p40-ia-ollama-llm.html
  - Guía completa de hardware 2026: https://freedium-mirror.cfd/https://medium.com/@paulhoke/the-complete-guide-to-running-large-language-models-locally-in-2026-hardware-tools-and-da9efb3170be
  - M5 MacBook Pro vs DGX Spark vs RTX PRO 6000: https://freedium-mirror.cfd/https://agentnativedev.medium.com/m5-macbook-pro-or-nvidia-dgx-spark-or-rtx-pro-6000-47480de9ec3a

---

## SECCIÓN 5 — Inferencia local: herramientas

### Diapositiva 5.1 — El mapa de herramientas
- **Título:** Tres niveles: terminal, app visual y servidor
- **Contenido:**
  - **llama.cpp** → el motor de bajo nivel (máximo control, compilas tú).
  - **Ollama / koboldcpp** → terminal sencilla, un comando y listo.
  - **LM Studio** → interfaz visual tipo ChatGPT.
  - **krasis** → orquestación/experimental.
  - Todas usan modelos en formato **GGUF** y permiten **servidor local** (API compatible OpenAI).
- **Imágenes:**
  - Logo llama.cpp: imagenes/logos/llamacpp.png
  - Logo Ollama: imagenes/logos/ollama.png
  - Logo LM Studio: imagenes/logos/lmstudio.png
  - Logo koboldcpp: imagenes/logos/koboldcpp.ico

### Diapositiva 5.2 — llama.cpp: el motor
- **Título:** llama.cpp — el corazón del ecosistema
- **Contenido:**
  - Motor en C/C++ que ejecuta GGUF en CPU y/o GPU. Base de Ollama y LM Studio.
  - **Compilar con soporte CUDA (pasos):**
    ```bash
    rm -Rf build
    # Ajusta DCMAKE_CUDA_COMPILER a tu versión de CUDA
    cmake -B build \
      -DGGML_CUDA=ON \
      -DCMAKE_CUDA_COMPILER=/usr/local/cuda-13.3/bin/nvcc \
      -DCMAKE_CUDA_ARCHITECTURES=native \
      -DCMAKE_BUILD_TYPE=Release \
      -DLLAMA_BUILD_TESTS=OFF \
      -DLLAMA_BUILD_EXAMPLES=OFF \
      -DGGML_CUDA_FA_ALL_QUANTS=ON \
      -DGGML_NATIVE=ON
    cmake --build build --config Release -j$(nproc)
    ```
  - Conceptos: **KV-cache** (memoria de la conversación), offload de capas a GPU (`-ngl`).
- **Imágenes:**
  - Logo llama.cpp: imagenes/logos/llamacpp.png
- **Enlaces:**
  - Optimización de inferencia local: https://carteakey.dev/blog/local-inference/local-llm-optimization/
  - KV-cache y jerarquía de memoria: https://touchdown-labs.com/blog/kv-cache-memory-hierarchy-inference.html
  - Modelo 35B en 6 GB VRAM (guía Qwen3): https://freedium-mirror.cfd/https://piedpay.medium.com/running-a-35b-large-model-local-ai-agent-on-6gb-vram-the-complete-deployment-guide-for-qwen3-6-35-7513982c19c3

### Diapositiva 5.3 — Ollama (y koboldcpp): un comando y listo
- **Título:** Ollama — la vía rápida desde la terminal
- **Contenido:**
  - Empaqueta modelos gigantes (Llama, modelos de código) y los ejecuta desde la terminal.
  - **Paso a paso:**
    1. Descarga Ollama gratis desde la web oficial.
    2. Abre tu terminal.
    3. `ollama run llama3.2` (o el modelo que prefieras). Modelo grande: `ollama run llama3.2-vision:90b`.
  - **Ejemplos de uso (multimodal):** preguntas simples, interpretar una receta médica manuscrita, analizar un ticket de compra, leer un gráfico de barras, contar gatos en una foto.
  - **koboldcpp:** alternativa con UI, popular para roleplay y control fino.
- **Imágenes:**
  - Web de Ollama: `imagenes/capturas/p3-000.png`
  - Terminal `ollama run llama3.2`: `imagenes/capturas/p4-001.png`
  - Análisis de ticket/recibo y gráfico de barras: `imagenes/capturas/p5-000.png`
- **Enlaces:**
  - koboldcpp: https://github.com/lostruins/koboldcpp

### Diapositiva 5.4 — LM Studio: interfaz visual
- **Título:** LM Studio — la experiencia calcada a ChatGPT
- **Contenido:**
  - App de escritorio (Mac/Windows/Linux): busca modelos, descarga con un clic y chatea.
  - **Pasos:**
    1. ¿Aguanta tu equipo? (16 GB ideal, 8 GB justo).
    2. Instala desde lmstudio.ai.
    3. Descarga tu primer modelo desde Hugging Face (ej. `Meta-Llama-3.1-8B-Instruct`). **Elige versiones cuantizadas `Q4_K_M`**.
    4. Carga el modelo y chatea. Aviso: si la memoria sale en **rojo**, no lo intentes.
  - Levanta un **servidor local** (API compatible OpenAI) para conectar editores.
- **Imágenes:**
  - LM Studio "Your local AI toolkit": `imagenes/capturas/p6-001.png`
  - Selector de modelo con `Q4_K_M` y barra de memoria: `imagenes/capturas/p8-000.png`
  - Chat en LM Studio: `imagenes/capturas/p9-001.png`
  - Icono Hugging Face: imagenes/logos/huggingface.svg
- **Enlaces:**
  - Descarga: https://lmstudio.ai

### Diapositiva 5.5 — Conectar la IA local a tu editor (VS Code)
- **Título:** La magia: tu copiloto local en VS Code
- **Contenido:**
  - Ollama y LM Studio levantan un **servidor local**; le dices a la extensión de copiloto: *"no uses la API de OpenAI, conéctate al modelo de mi ordenador"*.
  - Flujo (AI Toolkit / Copilot en VS Code): instala la extensión → catálogo de modelos → filtra **"local"** (CPU/GPU/NPU) → Añadir → "Gestionar modelos".
  - Resultado: asistente que revisa tu código y autocompleta **de forma privada y sin pagar a terceros**.
- **Imágenes:**
  - AI Toolkit + catálogo "Find the Right Model" (local CPU/GPU/NPU): `imagenes/capturas/p10-003.png` y `imagenes/capturas/p10-004.png`
  - "Manage Language Models" / Foundry Local: `imagenes/capturas/p12-005.png`
  - Icono GitHub Copilot: imagenes/logos/githubcopilot.svg

### Diapositiva 5.6 — Modelos recomendados para código en local
- **Título:** Qué modelo elegir para programar
- **Contenido (qué corre de verdad en consumo — fuente: AlexAImaginator / @TraffAlex, guía llama.cpp jun. 2026):**

  | Modelo | VRAM | Mejor para |
  |---|---|---|
  | **Gemma 4-12B** (Google) | 8-16 GB | All-rounder; el más listo de su tamaño. MTP GGUF 162 tok/s (3×) |
  | **LFM2.5-8B-A1B** (LiquidAI) | 8-12 GB | MoE híbrido (1B activo); rapidísimo y barato |
  | **Qwen3.6-27B** (Qwen) | 16-32 GB | Mejor agente local: 1.00 en tool-efficiency, tests 32k/128k |
  | **Qwopus3.6-27B-v2** (Jackrong) | 16-32 GB | Mejor cuantización Q4; top en 5 benchmarks de agentes/coding |
  | **Gemma 4-31B QAT** (Google/Unsloth) | 16-32 GB | QAT + MTP: 76-125 tok/s; multi-agente |
  | **Nex-N2-Mini** (Nex AGI) | 16 GB+ | MoE 3B activo (de Qwen3.5-35B); razonamiento profundo multi-paso |

  - **Quick picks:** 16 GB → Gemma 4-12B (MTP) · 32 GB → Qwen3.6-27B / Qwopus-v2 · agentes y tools → Qwopus Q4 · razonamiento → Nex-N2-Mini · presupuesto ajustado → LFM2.5-8B-A1B.
  - Build más barata: 1× RTX 3090 usada (24 GB) + resto del PC ≈ $1000-1500. Todos corren con **llama.cpp** (un comando; `Q4_K_M` / `Q5_K_M`).
  - Otros para bajos recursos: **JetBrains Mellum2-12B-A2.5B** (agente de código) · **VibeThinker-3B** (razonamiento ligero).
- **Imágenes:**
  - Icono Qwen: imagenes/logos/qwen.png
  - Icono DeepSeek: imagenes/logos/deepseek.png
- **Enlaces:**
  - Guía «Best Local LLMs for Consumer GPUs» (TraffAlex, jun. 2026): https://x.com/TraffAlex/status/2066236717015728227
  - Gemma 4-12B GGUF (Unsloth): https://huggingface.co/unsloth/gemma-4-12b-it-GGUF
  - LFM2.5-8B-A1B GGUF (LiquidAI): https://huggingface.co/LiquidAI/LFM2.5-8B-A1B-GGUF
  - Qwen3.6-27B GGUF (Unsloth): https://huggingface.co/unsloth/Qwen3.6-27B-GGUF
  - Qwopus3.6-27B-v2 GGUF (Jackrong): https://huggingface.co/Jackrong/Qwopus3.6-27B-v2-GGUF
  - Gemma 4-31B QAT GGUF (Unsloth): https://huggingface.co/unsloth/gemma-4-31B-it-qat-GGUF
  - Nex-N2-Mini GGUF: https://huggingface.co/sjakek/Nex-N2-mini-GGUF
  - 7 familias locales para reemplazar Codex: https://freedium-mirror.cfd/https://pub.towardsai.net/7-local-llm-families-to-replace-gpt-5-4-codex-for-everyday-tasks-37e8000bd751
  - JetBrains Mellum2-12B: https://huggingface.co/JetBrains/Mellum2-12B-A2.5B-Instruct
  - Por qué Mellum2 es el mejor coding LLM de bajos recursos: https://freedium-mirror.cfd/https://medium.com/artificial-intel-ligence-playground/jetbrains-mellum2-is-the-best-low-resources-local-coding-agent-llm-e7ead8d02b4e
  - VibeThinker-3B: https://huggingface.co/WeiboAI/VibeThinker-3B
  - DiffusionGemma 26B MoE (GGUF): https://huggingface.co/unsloth/diffusiongemma-26B-A4B-it-GGUF
  - krasis (orquestación): https://github.com/brontoguana/krasis
  - free-claude-code: https://github.com/Alishahryar1/free-claude-code

---

## SECCIÓN 6 — Servir modelos en producción

### Diapositiva 6.1 — De "mi portátil" a "varios usuarios"
- **Título:** vLLM y AnythingLLM: pasar a producción
- **Contenido:**
  - **vLLM:** motor de inferencia de alto rendimiento para servir modelos a escala. **PagedAttention** + batching continuo → mucho mayor throughput y varios usuarios concurrentes. Expone API compatible con OpenAI.
  - **AnythingLLM:** aplicación todo-en-uno (chat + **RAG** sobre tus documentos + agentes). Se conecta a Ollama, LM Studio o vLLM. Ideal para equipos.
  - Arquitectura típica: vLLM (servidor de modelo) → AnythingLLM (interfaz + RAG) → usuarios.
- **Imágenes:**
  - Logo vLLM: imagenes/logos/vllm.png
  - Logo AnythingLLM: imagenes/logos/anythingllm.png
- **Enlaces:**
  - Guía Ollama + LM Studio + AnythingLLM (2026): https://freedium-mirror.cfd/https://medium.com/startup-insider-edge/running-private-ai-locally-ollama-lm-studio-anythingllm-2026-guide-9b4659955419

---

## SECCIÓN 7 — RAG: qué es y por qué importa

### Diapositiva 7.1 — El problema: la ventana de contexto no es memoria
- **Título:** "El contexto es una pizarra que se borra en cada sesión"
- **Contenido:**
  - Un LLM olvida todo al cerrar la conversación. El contexto es limitado y temporal.
  - **RAG (Retrieval-Augmented Generation):** memoria externa persistente. El modelo *consulta* tus documentos antes de responder.
  - Idea fuerza: respuestas basadas en TUS datos (privados, actualizados) sin reentrenar el modelo.
- **Imágenes:**
  - `imagenes/diagramas/7-1-contexto-vs-memoria.svg`

### Diapositiva 7.2 — Cómo funciona RAG (el pipeline)
- **Título:** Embed → Store → Retrieve → Generate
- **Contenido:**
  1. **Chunking:** se trocean los documentos.
  2. **Embeddings:** cada trozo se convierte en un vector (representación numérica del significado).
  3. **Vector DB:** se guardan en una base vectorial (Chroma, Pinecone, Qdrant).
  4. **Retrieval:** ante una pregunta, se recuperan los trozos más cercanos.
  5. **Generate:** esos trozos se inyectan en el prompt y el modelo responde.
- **Imágenes:**
  - `imagenes/diagramas/7-2-rag-pipeline.svg`
- **Demo sugerida:** subir un PDF a AnythingLLM y preguntar sobre su contenido (todo local).

### Diapositiva 7.3 — RAG vs. Wiki vs. Skills (cuándo usar cada uno)
- **Título:** Tres formas de dar memoria a un agente
- **Contenido (tabla — fuente ai.gopubby):**

  | Si tu trabajo es… | Mejor arquitectura |
  |---|---|
  | Recuperar respuestas de un corpus grande y cambiante | **RAG** |
  | Construir conocimiento que se acumula con el tiempo | **LLM Wiki** (Karpathy) |
  | Actuar de forma autónoma sin que se lo pidas | **Fat Skills** (gBrain) |

  - **Clave:** no compiten, se combinan. RAG escala a 100.000+ documentos pero "no aprende"; la Wiki sintetiza y compone; las Skills actúan.
  - *(La LLM Wiki de Karpathy se amplía en la Sección 11.)*
- **Enlaces:**
  - RAG, LLM-Wiki o gBrain — cómo recuerda tu agente: https://freedium-mirror.cfd/https://ai.gopubby.com/rag-llm-wiki-or-gbrain-how-your-agent-remembers-changes-everything-56829e66725c

---

## SECCIÓN 8 — Agentes de código: "la IA escribe código por mí"

### Diapositiva 8.1 — Del autocompletado al agente autónomo
- **Título:** De copiloto a agente: deja que la IA ejecute
- **Contenido:**
  - **Autocompletado:** sugiere la siguiente línea.
  - **Chat:** le preguntas y copias/pegas.
  - **Agente:** lee tu repo, planifica, **edita varios archivos, ejecuta comandos, corre tests** y corrige solo.
  - Esto se volvió viable en 2025 con **RLVR** (Reinforcement Learning from Verifiable Rewards) → agentes que "mostly-work".
  - Ejemplos de agentes: Claude Code, Aider, OpenClaw, y harnesses propios.
- **Imágenes:**
  - `imagenes/diagramas/8-1-agente-loop.svg`

### Diapositiva 8.2 — Los agentes de código que puedes usar (CLIs e IDEs)
- **Título:** Los agentes que puedes usar hoy
- **Contenido (4 herramientas):**
  - **OpenCode:** open source, TUI en terminal. **Model-agnostic** → lo apuntas a tu Ollama / LM Studio / vLLM local. *Es el de la práctica del Bloque 3.*
  - **Claude Code:** CLI de Anthropic. El más potente: **Skills, MCP y subagentes**. Modelos en la nube (Claude).
  - **Gemini CLI:** CLI open source de Google. **Capa gratuita generosa** con Gemini; soporta MCP.
  - **Antigravity:** IDE agéntico de Google. Orquesta **varios agentes** + control del navegador; no solo terminal.
  - Clave: todos hablan el mismo idioma (**API compatible OpenAI / MCP**) → se apuntan a un modelo local o a la nube.
- **Enlaces:**
  - OpenCode: https://opencode.ai/
  - Claude Code: https://claude.com/claude-code
  - Gemini CLI: https://github.com/google-gemini/gemini-cli
  - Antigravity (Google): https://antigravity.google/

### Diapositiva 8.3 — Metodología: que el agente trabaje con método
- **Título:** GSD y Superpowers: dar disciplina al agente
- **Contenido:**
  - El problema de "tirar prompts a ciegas": el agente divaga, no verifica, rompe cosas.
  - **GSD (Get Stuff Done):** flujo estructurado (discutir → planificar → ejecutar → verificar) con commits atómicos y checkpoints.
  - **Superpowers (obra):** colección de skills/workflows que dan superpoderes reproducibles al agente.
  - Idea: **proceso sobre prosa**; pasos con criterio de salida y evidencia, no ensayos.
- **Imágenes:**
  - Icono GitHub Copilot: imagenes/logos/githubcopilot.svg
- **Enlaces:**
  - GSD Core: https://github.com/open-gsd/gsd-core
  - Superpowers (obra): https://github.com/obra/Superpowers
  - Hilo sobre agentes de código: https://x.com/filicroval/status/2052753382079651864

---

## SECCIÓN 9 — Agentes, Skills, MCP, Loops: la nomenclatura que da poder

### Diapositiva 9.1 — El vocabulario imprescindible
- **Título:** 4 conceptos que lo desbloquean todo
- **Contenido:**
  - **Agente:** un LLM + herramientas + un bucle que decide qué hacer.
  - **Skill:** un workflow en Markdown (pasos + criterios de salida) que el agente sigue.
  - **MCP:** protocolo estándar para conectar el agente a datos y herramientas externas.
  - **Loop:** el bucle de ejecución (percibir → decidir → actuar → observar) que repite hasta cumplir el objetivo.
- **Imágenes:**
  - `imagenes/diagramas/9-1-agente-componentes.svg`

### Diapositiva 9.2 — Agent Skills: workflows, no documentación
- **Título:** Skills: "proceso sobre prosa"
- **Contenido:**
  - Un **Skill** es un archivo Markdown con frontmatter que inyecta un workflow ejecutable: secuencia de pasos, checkpoints con evidencia y un criterio de salida.
  - 5 principios (Addy Osmani):
    1. **Proceso sobre prosa** — workflows que se ejecutan, no ensayos.
    2. **Tablas anti-racionalización** — respuestas a las excusas del modelo.
    3. **Verificación innegociable** — terminar con evidencia concreta.
    4. **Divulgación progresiva** — activar solo lo relevante (ahorra tokens).
    5. **Disciplina de alcance** — tocar solo lo pedido.
- **Imágenes:**
  - *(captura a tomar: ejemplo de un archivo SKILL.md con frontmatter)* — fuente: https://addyosmani.com/blog/agent-skills/
- **Enlaces:**
  - Agent Skills (Addy Osmani): https://addyosmani.com/blog/agent-skills/
  - "Probablemente usas los Skills mal": https://notes.ansonbiggs.com/youre-probably-using-agent-skills-wrong/
  - Directorios de skills: https://www.ui-skills.com/ · https://www.skills.sh/
  - Hilo de Akshay Pachaar: https://x.com/akshay_pachaar/status/2069404367497953592
  - Archivo de referencia: https://archive.ph/RDMCf
  - Skill para hacer esta presentación: https://github.com/zarazhangrui/frontend-slides

### Diapositiva 9.3 — MCP: el "USB-C" de la IA
- **Título:** Model Context Protocol — conecta todo, una sola vez
- **Contenido:**
  - **MCP** es un estándar abierto para conectar aplicaciones de IA a sistemas externos: datos (archivos, bases de datos), herramientas (buscadores, calculadoras) y workflows.
  - Analogía oficial: *"como un puerto USB-C para la IA"* — construye una vez, integra en todas partes.
  - Arquitectura: **cliente** (el agente) ↔ **servidor MCP** (expone *tools*, *resources*, *prompts*).
  - Soportado por Claude, ChatGPT, VS Code, Cursor… Ejemplos: acceder a tu Calendar/Notion, generar una web desde un diseño de Figma, imprimir en 3D desde Blender.
- **Imágenes:**
  - Diagrama oficial MCP: imagenes/logos/mcp-diagram.png
- **Enlaces:**
  - Introducción a MCP: https://modelcontextprotocol.io/docs/getting-started/intro
  - Curso de agentes (Hugging Face): https://huggingface.co/learn/agents-course/en/unit0/introduction
  - Harness Engineering: https://walkinglabs.github.io/learn-harness-engineering/en/

### Diapositiva 9.4 — Loops: agentes que trabajan solos
- **Título:** Loops y harness: del prompt único al trabajo continuo
- **Contenido:**
  - El **loop** es lo que convierte un LLM en agente: repite *decidir → actuar → observar* hasta cumplir el objetivo.
  - El **harness** es el código mínimo (~200 líneas) que gestiona ejecución, E/S de archivos y seguridad; las **skills** aportan la inteligencia del workflow ("fat skills, thin harness").
  - Con un **cron**, las skills se ejecutan de forma autónoma y programada.
- **Imágenes:**
  - `imagenes/diagramas/9-4-fat-skills-thin-harness.svg`
- **Enlaces:**
  - Guía moderna de web (Chrome): https://developer.chrome.com/docs/modern-web-guidance?hl=es-419

---

## SECCIÓN 10 — Montar tu propio asistente, de cero

### Diapositiva 10.1 — El objetivo: tu asistente personal, privado y persistente
- **Título:** De usar IA a tener TU asistente
- **Contenido:**
  - Juntamos todo: modelo local (Ollama/LM Studio) + skills + MCP + memoria.
  - Dos proyectos open source listos para empezar: **OpenClaw** (automatización generalista) y **Hermes** (agente que recuerda y aprende).
- **Imágenes:**
  - Icono Nous Research (Hermes): imagenes/logos/nousresearch.png

### Diapositiva 10.2 — OpenClaw: tu PC como asistente (gratis)
- **Título:** OpenClaw — automatiza tu ordenador
- **Contenido:**
  - Agente que corre en tu equipo y automatiza tareas: email, descargas, creación de contenido, automatización de negocio. Funciona en bucle continuo.
  - **Montarlo gratis (3 pasos):**
    1. Crea cuenta en **OpenRouter** y usa modelos gratuitos (o apunta a tu Ollama local).
    2. Edita el archivo de configuración para apuntar al modelo + credenciales.
    3. Lanza OpenClaw y prueba desde la interfaz de administración.
  - Extras: extensión de Chrome para automatizar web, gestión de memoria y skills desde **ClawHub**.
- **Imágenes:**
  - Icono OpenRouter (modelos gratis): imagenes/logos/openrouter.png
- **Enlaces:**
  - Guía OpenClaw gratis: https://freedium-mirror.cfd/https://pub.towardsai.net/a-beginner-friendly-guide-to-running-openclaw-for-free-04459be33ca0
  - Hilos: https://x.com/shannholmberg/status/2055335043904492011 · https://x.com/akshay_pachaar/status/2054564519280804028

### Diapositiva 10.3 — Hermes: el agente que recuerda lo de ayer
- **Título:** Hermes — un agente que escribe su propio manual
- **Contenido:**
  - Open source y self-hosted (Nous Research). Convierte tareas exitosas en **skills reutilizables** → hasta **40 % más rápido** tras uso sostenido.
  - **Memoria en 4 niveles:**
    1. Notas personales (~800 tokens) — hechos del entorno al arrancar.
    2. Perfil de usuario (~500 tokens) — preferencias y estilo.
    3. Búsqueda de sesiones — base SQLite con histórico completo.
    4. Plugins de memoria externa — grafos para uso empresarial.
  - **Seguridad:** genera sus skills desde TUS workflows (no descarga código de registros externos) → evita ataques de supply-chain. Aislamiento en contenedor + escaneo de prompt injection.
  - **Setup:** script bash (Linux/macOS/WSL2). Model-agnostic: Anthropic, OpenAI, DeepSeek o **local vía Ollama**. Gateways a Telegram/Slack/Discord.
- **Imágenes:**
  - Icono Nous Research: imagenes/logos/nousresearch.png
  - `imagenes/diagramas/10-3-hermes-memoria.svg`
- **Enlaces:**
  - Hermes recuerda lo de ayer: https://freedium-mirror.cfd/@creativeaininja/hermes-agent-the-open-source-ai-agent-that-actually-remembers-what-it-learned-yesterday-278441cd1870
  - Hermes: hype, realidad y para quién: https://freedium-mirror.cfd/https://www.towardsdeeplearning.com/hermes-agent-the-hype-the-reality-and-who-should-actually-use-it-acc20bc94d32
  - Hermes vs OpenClaw para workflows personales: https://freedium-mirror.cfd/https://medium.com/data-science-collective/what-is-hermes-agent-and-why-its-better-than-openclaw-for-personal-ai-workflows-d59d83436ad2

---

## SECCIÓN 11 — Más allá de los LLM

### Diapositiva 11.1 — Pinokio: instalar IA sin pelearte con la terminal
- **Título:** Pinokio — un "app store" para IA local
- **Contenido:**
  - Navegador/instalador que monta apps de IA (generación de imagen, audio, vídeo, LLMs) con **un clic**, gestionando dependencias por ti.
  - Ideal para probar herramientas sin configurar entornos a mano.
- **Imágenes:**
  - Logo Pinokio: imagenes/logos/pinokio.png

### Diapositiva 11.2 — IA en dispositivos pequeños y casos especializados
- **Título:** IA más allá del chat: del edge al CAD
- **Contenido:**
  - Modelos diminutos corriendo en **Raspberry Pi, móviles y NPUs** (edge AI): asistentes offline, visión, sensores.
  - **GenCAD:** IA generativa que produce **modelos CAD** a partir de descripciones/imágenes → la IA no solo escribe texto, también diseña objetos.
  - Mensaje: el ecosistema local va más allá del LLM de chat.
- **Imágenes:**
  - Figura de GenCAD (ejemplos de piezas generadas): imagenes/logos/gencad.png
  - Icono Raspberry Pi: imagenes/logos/raspberrypi.svg
- **Enlaces:**
  - GenCAD: https://github.com/ferdous-alam/GenCAD

### Diapositiva 11.3 — La memoria de Karpathy: tu segundo cerebro
- **Título:** "La IA compila el territorio; tú aún tienes que recorrerlo"
- **Contenido:**
  - Karpathy dejó de usar la IA solo para escribir código y la usa para construir un **segundo cerebro**: una **wiki LLM** auto-mantenida en Markdown.
  - **3 capas:** `/raw/` (fuentes inmutables) → schema (`CLAUDE.md` con las reglas) → wiki generada (resúmenes, páginas de entidades, backlinks).
  - **Operaciones:** *Ingest* (añadir material), *Query* (buscar), *Lint* (arreglar enlaces huérfanos/datos obsoletos).
  - Ventaja sobre RAG: el conocimiento **se acumula** y queda en Markdown legible, sin bases vectoriales ni cajas negras.
  - Conecta con Obsidian: tu vault como grafo de conocimiento "que piensa".
- **Imágenes:**
  - Icono Obsidian: imagenes/logos/obsidian.svg
  - `imagenes/diagramas/11-3-karpathy-wiki.svg`
- **Enlaces:**
  - Karpathy y el segundo cerebro: https://freedium-mirror.cfd/https://medium.com/neuralnotions/andrej-karpathy-stopped-using-ai-to-write-code-hes-using-it-to-build-a-second-brain-instead-cddceadc5df5
  - Harness personal (LLM Wiki en Obsidian): https://freedium-mirror.cfd/https://medium.com/@roanmonteiro/building-a-complete-personal-harness-llm-wiki-developers-second-brain-in-obsidian-d7b61c7398ff
  - Tu vault de Obsidian es un grafo de conocimiento: https://freedium-mirror.cfd/https://medium.com/graph-praxis/your-obsidian-vault-is-a-knowledge-graph-heres-how-to-make-it-think-quickly-1487614a7682

---

## SECCIÓN 12 — Conclusión

### Diapositiva 12.1 — Lo que SÍ puedes hacer en local hoy
- **Título:** Lo que ya puedes hacer en tu ordenador (2026)
- **Contenido:**
  - ✅ Programar con un copiloto privado en VS Code (Ollama/LM Studio).
  - ✅ Chatear y analizar imágenes/documentos (modelos multimodales).
  - ✅ Montar un **RAG** sobre tus propios documentos (AnythingLLM).
  - ✅ Ejecutar **agentes** que editan código y corren tests.
  - ✅ Tener un **asistente persistente** con memoria (Hermes, OpenClaw).
  - ✅ Construir tu **segundo cerebro** en Markdown.
- **Imágenes:**
  - `imagenes/diagramas/12-1-checklist.svg`

### Diapositiva 12.2 — El cambio de mentalidad
- **Título:** De tirar prompts a ciegas a controlar tu entorno
- **Contenido:**
  - Elegir bien el modelo y dónde ejecutarlo marca la diferencia entre tirar prompts a ciegas y tener el control técnico de tu entorno.
  - Privacidad + coste cero + offline + control = soberanía sobre tu IA.
  - Tu turno: **descarga una herramienta hoy y prueba cómo rinde tu máquina.**
- **Imágenes:**
  - *(diapositiva de texto; sin imagen)*

---

## SECCIÓN 13 — Apéndice

### Diapositiva 13.1 — Recursos para seguir aprendiendo
- **Título:** Apéndice: recursos y referencias
- **Contenido:**
  - **20 conceptos de IA en 20 minutos** — repaso rápido de vocabulario.
  - **Curso de prompt engineering** — escribir mejores instrucciones.
  - **Curso de agentes (Hugging Face)** — construir agentes paso a paso.
  - **Harness Engineering** — diseñar el bucle/armazón de tus agentes.
- **Imágenes:**
  - Icono Hugging Face: imagenes/logos/huggingface.svg
- **Enlaces:**
  - 20 conceptos de IA: https://freedium-mirror.cfd/https://medium.com/lets-code-future/20-most-important-ai-concepts-explained-in-just-20-minute-b7dd3ad2b506
  - Curso de prompt engineering: https://gs-run.github.io/prompt-engineering-course/index.html
  - Hilo de referencia: https://x.com/chesny/status/2068396516016824803 (recursos adicionales)
  - Curso de agentes (HF): https://huggingface.co/learn/agents-course/en/unit0/introduction
  - Harness Engineering: https://walkinglabs.github.io/learn-harness-engineering/en/

### Diapositiva 13.2 — Glosario rápido
- **Título:** Glosario de bolsillo
- **Contenido:**
  - **Token:** trozo de palabra que procesa el modelo.
  - **Contexto:** memoria temporal de la conversación.
  - **GGUF:** formato de archivo de modelo para llama.cpp/Ollama/LM Studio.
  - **Cuantización (Q4_K_M):** comprimir pesos para que pese menos.
  - **MoE:** modelo que activa solo parte de sus "expertos" por token.
  - **VRAM / ancho de banda:** la memoria de la GPU y su velocidad (el cuello de botella).
  - **RAG:** dar al modelo memoria externa sobre tus documentos.
  - **Agente / Skill / MCP / Loop:** ver Sección 9.
- **Imágenes:**
  - *(tabla/diapositiva de texto, sin imagen)*

### Diapositiva 13.3 — Cierre
- **Título:** ¡Gracias! Empieza hoy mismo
- **Contenido:**
  - Recordatorio: descarga Ollama o LM Studio y corre tu primer modelo esta semana.
  - Ponente: **José L. Redrejo Rodríguez** · Workshop «Monta tu IA Local» · IRIA, Almendralejo.
- **Imágenes:**
  - Logos: `imagenes/logos/ollama.png` · `imagenes/logos/lmstudio.png` · `imagenes/logos/huggingface.png`

---

## Apéndice técnico — Índice de imágenes usadas

**Capturas limpias de apps (`imagenes/capturas/`):**
- `estadistica_programacion.png` — estadísticas 2026 (84/41/36 %).
- `p5-000.png` — Ollama analizando un ticket de compra.
- `p6-001.png` — LM Studio "Your local AI toolkit".
- `p8-000.png` — LM Studio: selector de modelo / barra de memoria (`Q4_K_M`).
- `p9-001.png` — chat en LM Studio.
- `p10-003.png` — AI Toolkit en VS Code.
- `p10-004.png` — catálogo de modelos local (CPU/GPU/NPU).
- `p12-005.png` — "Manage Language Models" / Foundry Local.
- *(otras disponibles: p3-000 web Ollama, p4-001 terminal, p4-002 receta, p5-001 gráfico, p6-000 gatos, p8-001 descargas)*

**Logos y diagramas (`imagenes/logos/` y `imagenes/diagramas/`):**
- Ollama: imagenes/logos/ollama.png
- LM Studio: imagenes/logos/lmstudio.png
- llama.cpp: imagenes/logos/llamacpp.png
- koboldcpp: imagenes/logos/koboldcpp.ico
- vLLM: imagenes/logos/vllm.png
- AnythingLLM: imagenes/logos/anythingllm.png
- MCP (diagrama): imagenes/logos/mcp-diagram.png
- GenCAD (figura): imagenes/logos/gencad.png
- Pinokio: imagenes/logos/pinokio.png
- Hugging Face: imagenes/logos/huggingface.svg
- Obsidian: imagenes/logos/obsidian.svg
- Raspberry Pi: imagenes/logos/raspberrypi.svg
- Anthropic: imagenes/logos/anthropic.svg
- GitHub Copilot: imagenes/logos/githubcopilot.svg
- Qwen: imagenes/logos/qwen.png
- DeepSeek: imagenes/logos/deepseek.png
- OpenRouter: imagenes/logos/openrouter.png
- Nous Research: imagenes/logos/nousresearch.png
