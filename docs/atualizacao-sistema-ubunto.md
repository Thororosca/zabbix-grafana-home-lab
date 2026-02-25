# Atualização do sistema operacional

## Objetivo
Garantir que o sistema operacional esteja atualizado antes da instalação dos serviços de monitoramento, evitando conflitos de dependências e problemas de compatibilidade.

## Ambiente
- Sistema operacional: Ubuntu Server 22.04 LTS
- Tipo: Máquina virtual

## Procedimento

```bash
sudo apt update && sudo apt upgrade -y
