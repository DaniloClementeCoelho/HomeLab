# Laboratório

Registro cronológico de testes, experimentos, hipóteses e resultados do HomeLab.

## Regras

- Registrar aqui testes e medições, inclusive tentativas que falharam.
- Consolidar configurações permanentes nos arquivos temáticos.
- Registrar mudanças definitivas também no `CHANGELOG.md`.

## 2026-07-18 — ComfyUI e geração local de imagens

### Objetivo

Validar geração local de imagens com GPU NVIDIA no servidor `homelab-ai01`.

### Ambiente

- Servidor: `homelab-ai01`
- GPU: NVIDIA GeForce GTX 1650 Max-Q, 4 GB VRAM
- RAM: 16 GB
- Sistema: Ubuntu Server 26.04 LTS
- Execução: Docker com GPU NVIDIA
- ComfyUI: `0.28.0`
- Frontend: `1.45.21`
- PyTorch: `2.13.0+cu130`
- CUDA do container: `13.0`

### Instalação e acesso

- ComfyUI instalado em container Docker.
- GPU reconhecida dentro do container.
- DynamicVRAM e offload assíncrono habilitados.
- Porta direta: `8188`.
- Proxy reverso configurado no Nginx Proxy Manager.
- Acesso local validado em `http://comfy.home`.
- Entrada adicionada no arquivo `hosts` do Windows para `comfy.home`.

### Modelo instalado

- `sd_xl_turbo_1.0_fp16.safetensors`
- Tamanho aproximado: 6,5 GB
- Diretório no host: `~/homelab/compose/comfyui/models/checkpoints`

### Teste 1 — SDXL Turbo

- Workflow: template SDXL Turbo text-to-image.
- Resultado: imagem gerada com sucesso.
- Tempo observado: aproximadamente 5 segundos.
- Conclusão: ComfyUI, CUDA, checkpoint e workflow estão funcionais.

### Limitações observadas

- VRAM disponível detectada pelo ComfyUI: aproximadamente 3,7 GB.
- A GPU não suporta confortavelmente modelos grandes integralmente em VRAM.
- Testes mais pesados dependerão de offload para RAM e CPU.
- O ComfyUI emitiu aviso de possível incompatibilidade com `cuda-malloc`; usar `--disable-cuda-malloc` somente se surgirem erros CUDA.

### Próximos testes

- SDXL Turbo em resolução maior.
- SDXL Base 1.0.
- Checkpoints SDXL realistas.
- FLUX.1-schnell quantizado em GGUF.
- Registrar tempo, resolução, passos, consumo de RAM/VRAM e qualidade percebida em cada teste.
