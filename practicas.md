Recomendación: instalar antes un editor para código. Recomendado https://zed.dev/
En windows: cuidado con el firewall, es muy posible que bloquee muchas de estas funcionalidades porque usan puertos TCP/IP. Para estas pruebas vendría bien desactivar el firewall.bloqu

✅ Práctica LM-Studio
- Descargar desde https://lmstudio.ai/download
- abrirlo y pulsar en el icono de la izquierda Model Search (icono de un robot)
- Explorar los modelos, descargar uno (dependiendo del ancho de banda de la wifi, puede tardar mucho: revisa el tamaño. Phi-3-mini es pequeño, 2.39GB, y funcional)
- Inicia el chat
- PUlsar el botón Developer (icono de un terminal): Load model y pulsar el icono de arriba pasando Status de "Stopped" a "Running": abrir un navegador en http://localhost:1234/api/v1/models

✅ Práctica RAG
- Crear un RAG local rápido:
    - Instalar https://docs.anythingllm.com/installation-desktop/windows#downloading-the-installation-file
    - Abrir Anything LLM -> icono llave (settings) ->Proveedores de IA -> LLM y seleccionar LM-Studio y el modelo que queramos de LM-Studio
    - Volver al chat (icono flecha de abajo) . Pulsar el icono de "Upload documents and... " (flecha con caja, junto al nombre del chat). Ahí se puede añadir documentos y moverlos al espacio de trabajo
    - Volver al chat y preguntar



✅ Práctica Opencode y skills

1. Instalación en Windows (opción más fácil):
- Descargar desde https://opencode.ai/download → Windows x64

2. Configurar múltiples backends editando C:\Users\<usuario>\AppData\Roaming\opencode\opencode.json:

{
  "provider": {
    "lmstudio": {
      "npm": "@ai-sdk/openai-compatible",
      "options": { "baseURL": "http://localhost:1234/v1" },
      "models": { "qwen2.5-coder:7b": { "name": "Qwen2.5-Coder 7B" } }
    },
    "vllm": {
      "npm": "@ai-sdk/openai-compatible",
      "options": { "baseURL": "http://10.10.10.62:8000/v1" },
      "models": { "Qwopus3.6-27B": { "name": "Qwopus3.6-27B" } }
    },
    "llama.cpp": {
      "npm": "@ai-sdk/openai-compatible",
      "options": { "baseURL": "http://<ip_servidor_rtx5090>:8000/v1" },
      "models": { "Qwopus3.6-27B": { "name": "Qwopus3.6-27B" } }
    }
  }
}

Alternativa: Descargar desde https://opengui.io/download → Windows y usarlo para configurar opencode


3. Crear un plan para hacer una web
4. Crear una presentación usando llama.cpp y el skill frontend-slides




✅  Práctica de Hermes

PARTE 1 — Instalar Hermes y conectar a LLM
Desde:
1. Desde https://hermes-agent.nousresearch.com/ descargar e instalar  hermes.
2. ejecutar
    hermes setup
    o
    hermes model
3. en el menú interactivo
    Selecciona "Custom / OpenAI-compatible endpoint"
    Introduce la URL base: http://localhost:1234/v1 (si usas tu propio ordenador) o "http://10.10.10.62:8000/v1" para usar el servidor de IRIA
    API Key: ollama (cualquier texto, Ollama no la valida)
    Nombre del modelo: llama3.2 (o el que hayas descargado) Qwopus3.6-27B si usas el servidor de iria o el que devuelva http://localhost:1234/api/v1/models si usas lm-studio

PARTE 2 — Crear el bot de Telegram ( https://hermes-agent.nousresearch.com/docs/user-guide/messaging/telegram )
1. Crear el bot con BotFather
Abre Telegram y busca @BotFather (o ve a t.me/BotFather). Envía /newbot, elige un nombre para mostrar (p.ej. "Mi Hermes") y un nombre de usuario que termine en bot (p.ej. mi_hermes_bot). BotFather te devolverá un token con este formato:
`123456789:ABCdefGHIjklMNOpqrSTUvwxYZ`  guarda este token, lo necesitarás enseguida
2. Obtener tu ID de usuario de Telegram
Envía un mensaje /start a @myidbot  te responde inmediatamente con tu ID numérico (p.ej. 123456789).
3. Configurar Hermes con el bot de Telegram. Ejecuta:
`hermes gateway setup`
Selecciona Telegram y sigue las preguntas: te pedirá el token y tu ID de usuario
4. Iniciar el gateway
`hermes gateway`
5. Probar: Abre Telegram, habla con tu bot y verifica que:
Responde (usa el modelo local de Ollama)
Puedes enviar mensajes de voz (se transcriben automáticamente)
Puedes pedirle tareas como buscar información o ejecutar código

Su alma:
C:\Users\TU_USUARIO\.hermes\SOUL.md
contiene información sobre como se va a comportar

PARTE 3: Setup completo
ejecuta
`hermes setup`
si quieres añadir más funcionalidades
