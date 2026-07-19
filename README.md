# HomeLab

Documentação oficial do HomeLab de Danilo Clemente Coelho.

## Objetivo

Manter uma plataforma doméstica para modelos locais de IA, automações, busca web, RAG, monitoramento e serviços auxiliares.

## Estado atual

O servidor principal já executa Ubuntu Server, Docker, GPU NVIDIA em containers, Ollama, Open WebUI, SearXNG, Qdrant, Homepage, Portainer, Nginx Proxy Manager e ComfyUI.

## Estrutura

- [00-HARDWARE.md](00-HARDWARE.md) — inventário físico
- [01-ARQUITETURA.md](01-ARQUITETURA.md) — arquitetura e fluxos
- [02-REDE.md](02-REDE.md) — rede, endereços e exposição de serviços
- [03-SERVIDORES.md](03-SERVIDORES.md) — estado operacional dos servidores
- [04-CONTAINERS.md](04-CONTAINERS.md) — containers e padrões Docker
- [05-AI.md](05-AI.md) — Ollama, Open WebUI, ComfyUI, modelos e RAG
- [06-AUTOMACOES.md](06-AUTOMACOES.md) — automações
- [07-BACKUP.md](07-BACKUP.md) — estratégia de backup
- [08-SEGURANCA.md](08-SEGURANCA.md) — segurança
- [09-JOGOS.md](09-JOGOS.md) — serviços de jogos
- [10-LAB.md](10-LAB.md) — diário de testes e experimentos
- [ROADMAP.md](ROADMAP.md) — próximos passos
- [CHANGELOG.md](CHANGELOG.md) — histórico de alterações permanentes

## Regra de documentação

Este repositório é a fonte da verdade do projeto. Mudanças relevantes, versões, testes e decisões devem ser registradas aqui para que novas conversas não dependam de um histórico extenso.

- Estado atual e configurações permanentes ficam nos arquivos temáticos.
- Testes, medições, hipóteses e tentativas ficam em `10-LAB.md`.
- Mudanças definitivas ficam também em `CHANGELOG.md`.
