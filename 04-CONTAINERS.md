# Containers

## Serviços em execução

- Ollama
- Open WebUI
- SearXNG
- Qdrant
- Homepage
- Portainer
- Nginx Proxy Manager

## Padrões adotados

- Docker Compose V2.
- Um diretório de Compose por serviço ou stack.
- Dados persistentes fora do arquivo `compose.yaml`.
- Comunicação interna pelo nome do serviço na rede Docker.
- Publicação web centralizada no Nginx Proxy Manager.
- GPU disponibilizada ao Ollama por meio do NVIDIA Container Toolkit.

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

## GPU

A validação do runtime NVIDIA foi concluída com uma imagem CUDA e `nvidia-smi` dentro do container.

## Diagnóstico

Sempre separar o teste em camadas:

1. Serviço diretamente no container.
2. Comunicação entre containers.
3. Interface web.
4. Proxy reverso.

Esse procedimento evita atribuir ao hardware problemas originados na interface ou integração.
