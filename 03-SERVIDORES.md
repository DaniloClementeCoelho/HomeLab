# Servidores

## homelab-ai01

- Equipamento: ASUS ZenBook Flip 15
- Sistema operacional: Ubuntu Server 26.04 LTS
- Função: servidor principal de containers e IA
- GPU: NVIDIA GTX 1650 Max-Q com CUDA habilitada

### Serviços atuais

- Docker
- Ollama
- Open WebUI
- SearXNG
- Qdrant
- Homepage
- Portainer
- Nginx Proxy Manager

### Validações concluídas

- `nvidia-smi` funcionando no host.
- GPU acessível dentro de container CUDA.
- Ollama detectando CUDA e usando offload parcial.
- Open WebUI atualizado e banco migrado sem erros.
- SearXNG respondendo em JSON.
- Homepage lendo estado dos containers pelo socket Docker.

## homelab-srv01

- Equipamento: HP EliteBook i5-5200U, 8 GB RAM
- Situação: disponível para serviços auxiliares
- Papel definitivo: ainda não definido

## homelab-net01

- Equipamento: HP i3-2328M, 4 GB RAM
- Situação: disponível para serviços leves
- Papel definitivo: ainda não definido
