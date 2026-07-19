# Servidores

## homelab-ai01 — servidor principal

### Identificação

- Hostname: `homelab01`
- Equipamento: ASUS ZenBook Flip 15 UX564EH/Q528EH
- Sistema operacional: Ubuntu Server 26.04 LTS
- IP estático: `192.168.15.9`
- Função: servidor principal de containers e IA
- GPU: NVIDIA GeForce GTX 1650 Max-Q, 4 GB VRAM

### Estado operacional

- Docker instalado e funcional.
- GPU NVIDIA acessível no host e em containers.
- NVIDIA Container Toolkit validado.
- Driver: `nvidia-driver-595-open`.

### Serviços atuais

| Serviço | Estado | Porta/acesso | Observações |
|---|---|---|---|
| Ollama | ativo | `11434` | CUDA e offload parcial |
| Open WebUI | ativo | via proxy | versão validada `0.10.2` |
| SearXNG | ativo | interno `8080` | API JSON validada |
| Qdrant | ativo | interno | banco vetorial para RAG |
| Homepage | ativo | via proxy | integração com socket Docker |
| Portainer | ativo | via proxy | gerenciamento de containers |
| Nginx Proxy Manager | ativo | `80`/`443` | proxy reverso local |
| ComfyUI | ativo | `8188` e `http://comfy.home` | GPU, DynamicVRAM e offload |

### Diretórios relevantes

```text
~/homelab
~/homelab/compose
~/homelab/compose/comfyui
~/homelab/compose/comfyui/models/checkpoints
```

### Validações concluídas

- `nvidia-smi` funcionando no host.
- GPU acessível dentro de container CUDA.
- Ollama detectando CUDA e usando offload parcial.
- Open WebUI atualizado e banco migrado sem erros.
- SearXNG respondendo em JSON.
- Homepage lendo o estado dos containers pelo socket Docker.
- ComfyUI reconhecendo a GTX 1650 Max-Q e gerando imagens com SDXL Turbo.
- Proxy `comfy.home` validado pelo Nginx Proxy Manager.

### Limitações operacionais

- Aproximadamente 3,7 GB de VRAM utilizável pelo ComfyUI.
- Modelos grandes dependem de offload para RAM e CPU.
- Modelos de 30B no Ollama funcionam com baixa velocidade.

## homelab-srv01

- Equipamento: HP EliteBook
- CPU: Intel Core i5-5200U, 2.20 GHz
- RAM: 8 GB
- Situação: disponível para serviços auxiliares
- Papel definitivo: ainda não definido

## homelab-net01

- Equipamento: HP
- CPU: Intel Core i3-2328M, 2.20 GHz
- RAM: 4 GB
- Situação: disponível para serviços leves de rede ou infraestrutura
- Papel definitivo: ainda não definido
