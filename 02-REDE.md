# Rede

## Topologia atual

```text
Internet
   |
Roteador Vivo Askey RTF8225VW-SV
LAN: 192.168.15.1/24
   |
   +-- homelab01
   |     IP estático: 192.168.15.10
   |
   +-- Eero
         WAN: 192.168.15.5
         LAN: 192.168.4.0/24
         Modo: roteador com DHCP/NAT
```

## Decisões de arquitetura

- O servidor HomeLab permanece conectado diretamente ao roteador Vivo.
- O Eero permanece operando como roteador independente.
- Os clientes Wi-Fi conectados ao Eero usam a rede `192.168.4.0/24`.
- O HomeLab usa a rede `192.168.15.0/24`.
- Essa separação é deliberada e não deve ser alterada sem nova decisão de arquitetura.

## Servidor principal

| Item | Configuração |
|---|---|
| Hostname | `homelab01` |
| Interface Ethernet | `enx00e04c882bfb` |
| Endereço MAC | `00:e0:4c:88:2b:fb` |
| IPv4 | `192.168.15.10/24` |
| Gateway | `192.168.15.1` |
| DNS primário | `8.8.8.8` |
| DNS secundário | `1.1.1.1` |
| Gerenciamento | NetworkManager (`nmcli`) |
| Conexão | `Wired connection 1` |

A interface Wi-Fi `wlo1` não é utilizada.

## Configuração de IP

O IPv4 estático foi configurado diretamente no NetworkManager. O arquivo Netplan existente gerencia apenas a interface Wi-Fi e não deve ser usado para alterar a Ethernet.

Objetivos da configuração estática:

- impedir mudanças de endereço após reinicializações;
- manter estáveis o acesso SSH e as URLs dos serviços;
- eliminar dependência de concessões DHCP do roteador Vivo.

## Acesso SSH

```bash
ssh danilocoelho@192.168.15.10
```
