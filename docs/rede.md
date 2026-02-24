# Configuração de Rede

A máquina virtual foi inicialmente configurada em modo NAT para acesso à internet.

Posteriormente, a configuração foi alterada para modo Bridge, permitindo que a VM recebesse um endereço IP da mesma faixa da rede física.

## Endereçamento
- Host (PC): 192.168.15.1
- VM (Zabbix Server): 192.168.15.35
- Interface: enp0s3
- Máscara: /24

## Objetivo da Configuração
Permitir monitoramento de dispositivos reais da rede local via ICMP, SNMP e agentes.
