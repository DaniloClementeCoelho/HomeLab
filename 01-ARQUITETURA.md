# Arquitetura

## Visão geral

```text
Usuário / navegador
        |
        v
Nginx Proxy Manager
        |
        +--> Open WebUI ----> Ollama ----> modelos locais
        |         |
        |         +--> SearXNG
        |         +--> Qdrant
        |
        +--> Homepage
        +--> Portainer
```

## Responsabilidades

### Nginx Proxy Manager

- Publicação dos serviços web.
- Centralização de nomes, certificados e proxy reverso.

### Open WebUI

- Interface principal para conversar com modelos locais.
- Integração com busca web, conhecimento, RAG e ferramentas.

### Ollama

- Execução e gerenciamento dos modelos locais.
- Uso de CUDA por meio da GPU NVIDIA.

### SearXNG

- Mecanismo de metabusca usado pelo Open WebUI.
- API JSON habilitada em `settings.yml`.

### Qdrant

- Banco vetorial previsto para documentos, embeddings e RAG.

### Homepage

- Painel de acesso e monitoramento dos serviços.
- Integração com o socket Docker para exibir estado e estatísticas.

### Portainer

- Administração visual do ambiente Docker.

## Princípios

- Docker Compose como padrão de implantação.
- Dados persistentes separados dos arquivos de Compose.
- Serviços internos acessados pelo nome do container na rede Docker.
- Exposição externa centralizada no Nginx Proxy Manager.
- O GitHub mantém a documentação e as decisões do ambiente.
