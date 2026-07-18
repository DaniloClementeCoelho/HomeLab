# Hardware

## homelab-ai01 — servidor principal

- Modelo: ASUS ZenBook Flip 15 UX564EH/Q528EH
- CPU: Intel Core i7-1165G7
- RAM: 16 GB DDR4
- GPU integrada: Intel Iris Xe
- GPU dedicada: NVIDIA GeForce GTX 1650 Max-Q, 4 GB VRAM
- Armazenamento: SSD NVMe de aproximadamente 512 GB
- Sistema operacional atual: Ubuntu Server 26.04 LTS
- Função: servidor principal de IA e containers

### Rede

- Hostname: `homelab01`
- IP estático: `192.168.15.9/24`
- Gateway: `192.168.15.1`
- DNS: `8.8.8.8` e `1.1.1.1`
- Interface Ethernet principal: `enx00e04c882bfb`
- Interface Wi-Fi: `wlo1` — não utilizada
- Gerenciamento de rede: NetworkManager (`nmcli`)

### Observações

- A GPU NVIDIA está operacional no host e em containers Docker.
- Driver adotado: `nvidia-driver-595-open`.
- NVIDIA Container Toolkit instalado e validado.
- O hardware permite executar modelos grandes com offload parcial para GPU, mas a maior parte do processamento de modelos de 30B permanece na CPU.
- O endereço IPv4 estático evita mudanças de IP após reinicializações e mantém estáveis o acesso SSH e os serviços do HomeLab.

## homelab-srv01

- Modelo: HP EliteBook
- CPU: Intel Core i5-5200U, 2.20 GHz
- RAM: 8 GB
- Sistema anterior: Windows 10 Pro, 32 bits em processador x64
- Função prevista: serviços auxiliares do HomeLab

## homelab-net01

- Modelo: HP
- CPU: Intel Core i3-2328M, 2.20 GHz
- RAM: 4 GB
- Sistema anterior: Windows 10 Pro 22H2, 32 bits em processador x64
- Função prevista: serviços leves de rede ou infraestrutura

## Equipamento em avaliação

- Dell Inspiron 13 7000 2-in-1, 2017

## Limitações conhecidas

- A GTX 1650 Max-Q possui somente 4 GB de VRAM.
- Modelos de 30B funcionam, mas com baixa velocidade e forte dependência de CPU e RAM.
- Para uso cotidiano, modelos de 7B ou 8B tendem a oferecer melhor experiência.