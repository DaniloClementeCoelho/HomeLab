# Changelog

## 2026-07-18

### Documentação

- Estrutura inicial do repositório criada.
- README atualizado com o estado atual do HomeLab.
- Inventário de hardware revisado.
- Arquitetura dos serviços documentada.
- Servidores e validações concluídas registrados.
- Padrões de containers e integrações documentados.
- Stack de IA, modelos e benchmark do `qwen3-coder:30b` registrados.
- Roadmap reorganizado em concluído, investigação e próximas etapas.
- Criado `10-LAB.md` para registrar testes, medições, hipóteses e resultados.
- `03-SERVIDORES.md` atualizado com o estado operacional do `homelab-ai01`.
- `04-CONTAINERS.md` atualizado com a configuração operacional do ComfyUI.
- `05-AI.md` atualizado com ambiente, modelo e teste inicial do ComfyUI.
- `05-AI.md` estruturado para inventariar custom nodes, checkpoints, LoRAs, VAEs, ControlNet, outros modelos e workflows do ComfyUI.

### Infraestrutura registrada

- Ubuntu Server 26.04 LTS no servidor principal.
- Driver `nvidia-driver-595-open`.
- NVIDIA Container Toolkit validado.
- GPU NVIDIA acessível no host e em containers.
- Ollama atualizado para `0.12.6`.
- Open WebUI atualizado para `0.10.2`.
- SearXNG com API JSON funcional.
- Homepage integrado ao socket Docker.
- ComfyUI `0.28.0` instalado em container Docker com GPU.
- ComfyUI Manager integrado e habilitado.
- DynamicVRAM e offload assíncrono detectados no ComfyUI.
- Checkpoint `sd_xl_turbo_1.0_fp16.safetensors` instalado em armazenamento persistente.

### Rede

- Configurado IPv4 estático no servidor principal.
- Endereço inicialmente definido como `192.168.15.10/24`.
- Detectado conflito de rede no endereço `192.168.15.10`.
- Endereço definitivo alterado para `192.168.15.9/24`.
- Gateway definido como `192.168.15.1`.
- DNS configurado como `8.8.8.8` e `1.1.1.1`.
- Interface Ethernet registrada como `enx00e04c882bfb`.
- Configuração realizada via NetworkManager (`nmcli`).
- Topologia Vivo, HomeLab e Eero documentada.
- Acesso SSH validado em `192.168.15.9`.
- Proxy local `http://comfy.home` configurado e validado no Nginx Proxy Manager.

### Diagnóstico registrado

- `qwen3-coder:30b` respondeu diretamente pelo Ollama em 42,126 segundos.
- Latência próxima de 10 minutos no Open WebUI permanece em investigação.
- Primeira imagem com SDXL Turbo gerada com sucesso em aproximadamente 5 segundos.
- ComfyUI detectou aproximadamente 3,7 GB de VRAM utilizável na GTX 1650 Max-Q.
