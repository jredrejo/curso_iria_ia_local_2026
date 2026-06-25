## COMPILACIÓN
```
rm -Rf build

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

Ejemplos de ejecución optimizados para distintas GPU:

# 12 gb VRAM
  ```
./llama-server \
  --model /models/gemma-4-31B-it-Q4_K_M.gguf \
  --alias Gemma4-Q4 \
  --host 0.0.0.0   --port 8000 --parallel 1 \
  --ctx-size 16384 --n-gpu-layers 35 \
  --cache-ram 2048 \
  --batch-size 512 \
  --ubatch-size 128 \
  --threads 8 \
  --threads-batch 8 \
  --cache-type-k q4_0 \
  --cache-type-v q4_0 \
  --temp 1.2 \
  --top-p 0.95 \
  --top-k 64 \
  --min-p 0.05 \
  --repeat-penalty 1.1 --parallel 1 \
  --flash-attn on \
  --no-context-shift  --reasoning-format none --jinja\
  --log-file /var/log/llama-server/llama-server.log
  ```
  ```
  ./llama-server \
  --model /home/jose/models/Qwen3.6-35B-A3B-Claude-4.7-Opus-Reasoning-Distilled-APEX-I-Nano.gguf \
  --alias Qwen3.6-35B \
  --host 0.0.0.0  --port 8000  \
  --ctx-size 49152   --n-predict 49152\
  --cache-ram 8192 \
  --batch-size 2048 \
  --ubatch-size 256 \
  --threads 10 \
  --threads-batch 10 --parallel 1 \
  --cache-type-k q4_0 \
  --cache-type-v q8_0 \
  --temp 0.15 \
  --top-p 0.9 \
  --top-k 40  --repeat-penalty 1.0   --reasoning off\
  --min-p 0.05  \
  --flash-attn on --no-context-shift --no-warmup \
  --jinja --chat-template-file /home/jose/models/chat_template.jinja \
 --log-file /var/log/llama-server/llama-server.log
   ```
# 32 GB VRAM
    ```
./build/bin/llama-server  --model   /models/SuperGemma4-31b-abliterated.Q4_K_M.gguf   --host 0.0.0.0 --port 8000 --alias "Gemma4"    --parallel 1    --temp 1.0     --top-p 0.95     --top-k 64     --metrics    --chat-template-kwargs '{"enable_thinking":true}' --threads 10 --ctx-size 131072 --jinja  --chat-template-file  ./chat_template_gemma4abliterated.jinja --no-warmup
    ```
    
    ```
  Qwopus3.6-27B-Coder-MTP-Q8_0.gguf  problema con loops
        ./llama-server \
--model /models/Qwopus3.6-27B-Coder-MTP-Q8_0.gguf \
--alias Qwopus3.6-27B \
--host 0.0.0.0  --port 8000  \
--threads 8 \
--threads-batch 8 --parallel 1 --kv-unified \
-ngl 99 -c 131072 --cache-ram 0 \
--cache-type-k f16 --cache-type-v f16 \
--flash-attn on -b 4096 -ub 1024 \
--jinja \
--reasoning off \
--chat-template-kwargs '{"preserve_thinking": false}' \
--chat-template-file /data/models/qwen_chat_template.jinja \
--temp 0.8 \
--top-p 0.95 \
--top-k 20 \
--min-p 0.0    --spec-type draft-mtp --spec-draft-n-max 3\
--log-file /var/log/llama-server/llama-server.log
 ```

```
./llama-server \
  --model /models/gemma-4-31B-it-UD-Q8_K_XL.gguf \
  --alias gemma-4-31B \
  --host 0.0.0.0  --port 8000  \
  --threads 8 \
  --threads-batch 8 --parallel 1 --kv-unified \
  -ngl 99 -c 131072 --cache-ram 0   \
  --cache-type-k q8_0 --cache-type-v q8_0 \
  --flash-attn on -b 2048 -ub 512 \
  --jinja --reasoning-budget 1024 \
  --reasoning on --presence-penalty 1.1 \
  --chat-template-kwargs '{"preserve_thinking": true}' \
  --temp 1 \
  --top-p 0.95 \
  --top-k 64 \
  --min-p 0.0 \
  --log-file /var/log/llama-server/llama-server.log
 ```
