# Containers

## Serviços em execução

- Ollama
- Open WebUI
- SearXNG
- Qdrant
- Homepage
- Portainer
- Nginx Proxy Manager
- ComfyUI

## Padrões adotados

- Docker Compose V2.
- Um diretório de Compose por serviço ou stack.
- Dados persistentes fora do arquivo `compose.yaml`.
- Comunicação interna pelo nome do serviço na rede Docker.
- Publicação web centralizada no Nginx Proxy Manager.
- GPU disponibilizada aos serviços de IA por meio do NVIDIA Container Toolkit.

## Homepage

Configuração funcional do socket Docker:

```yaml
# docker.yaml
my-docker:
  socket: /var/run/docker.sock
```

O socket precisa estar montado no container Homepage.

## SearXNG

Para integração com o Open WebUI, o arquivo `settings.yml` deve permitir JSON:

```yaml
search:
  formats:
    - html
    - json
```

URL interna usada pelo Open WebUI:

```text
http://searxng:8080/search
```

## ComfyUI

- Diretório da stack: `~/homelab/compose/comfyui`.
- Porta publicada: `8188`.
- Acesso pelo proxy local: `http://comfy.home`.
- GPU NVIDIA disponível dentro do container.
- DynamicVRAM e offload assíncrono detectados e habilitados.
- ComfyUI Manager integrado, habilitado na inicialização.

### Persistência de modelos

Diretório de checkpoints no host:

```text
~/homelab/compose/comfyui/models/checkpoints
```

Checkpoint atualmente instalado:

```text
sd_xl_turbo_1.0_fp16.safetensors
```

Os modelos devem permanecer em diretórios persistentes no host, fora da camada gravável do container, para não serem perdidos em recriações ou atualizações.

## GPU

A validação do runtime NVIDIA foi concluída com uma imagem CUDA e `nvidia-smi` dentro do container.

O ComfyUI detectou aproximadamente 3,7 GB de VRAM utilizável na GTX 1650 Max-Q. Modelos que ultrapassem esse limite dependerão de offload para RAM e CPU.

## Diagnóstico

Sempre separar o teste em camadas:

1. Serviço diretamente no container.
2. Comunicação entre containers.
3. Interface web.
4. Proxy reverso.

Esse procedimento evita atribuir ao hardware problemas originados na interface ou integração.
