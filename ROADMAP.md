# Roadmap

## Concluído

- [x] Instalar Ubuntu Server no servidor principal.
- [x] Instalar Docker e Docker Compose.
- [x] Instalar driver NVIDIA aberto.
- [x] Instalar NVIDIA Container Toolkit.
- [x] Validar GPU no host e em containers.
- [x] Instalar e atualizar Ollama.
- [x] Instalar modelos locais.
- [x] Instalar e atualizar Open WebUI.
- [x] Instalar SearXNG e habilitar resposta JSON.
- [x] Instalar Qdrant.
- [x] Instalar Homepage e integrar com Docker.
- [x] Instalar Portainer.
- [x] Instalar Nginx Proxy Manager.

## Em investigação

- [ ] Medir a latência entre Open WebUI e Ollama usando logs simultâneos.
- [ ] Identificar por que o `qwen3-coder:30b` tenta usar ferramentas inadequadas.
- [ ] Comparar o mesmo prompt no `qwen3:8b` e no `qwen3-coder:30b`.
- [ ] Validar uma configuração sem ferramentas no Workspace Model.

## Próximas etapas

### IA e conhecimento

- [ ] Configurar RAG com Open WebUI, `nomic-embed-text` e Qdrant.
- [ ] Criar modelos de Workspace especializados.
- [ ] Definir política de uso dos modelos por tipo de tarefa.
- [ ] Testar ingestão e recuperação de documentos.

### Operação

- [ ] Documentar IPs, portas, redes Docker e nomes internos.
- [ ] Definir estratégia de backup dos volumes.
- [ ] Implementar monitoramento e alertas.
- [ ] Revisar atualizações e fixação de versões das imagens.

### Expansão

- [ ] Definir função para os notebooks HP.
- [ ] Avaliar NAS.
- [ ] Avaliar n8n e integrações MCP.
- [ ] Avaliar cluster somente após estabilizar o servidor principal.
