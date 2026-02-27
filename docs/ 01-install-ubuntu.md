🖥️ Ambiente Inicial

Este documento descreve a estrutura base utilizada para implantação do laboratório de monitoramento com Zabbix e Grafana.

O ambiente foi construído utilizando virtualização local, permitindo simular um cenário de servidor real dentro de infraestrutura doméstica.

---

🔹 Plataforma de Virtualização

Para a criação da máquina virtual foi utilizado o:

Hypervisor: Oracle VM VirtualBox
Download oficial: https://www.virtualbox.org/wiki/Downloads

O VirtualBox foi escolhido por ser uma solução gratuita, amplamente utilizada para laboratórios e testes, permitindo simulação de ambientes de servidor sem necessidade de hardware dedicado.

---


🔹 Sistema Operacional

A máquina virtual foi instalada com:

Distribuição: Ubuntu Server 24.04 LTS
Download oficial: https://ubuntu.com/download/server

Características da instalação:

Versão LTS (Long Term Support), garantindo suporte estendido e estabilidade

Interface exclusivamente CLI (sem ambiente gráfico)

Kernel Linux 6.8.x

Instalação mínima para reduzir consumo de recursos e superfície de ataque

A escolha do Ubuntu Server se deve à sua ampla utilização em ambientes corporativos, grande comunidade e compatibilidade com ferramentas como Zabbix, MariaDB e Grafana.

---

🔹 Configuração da Máquina Virtual
Recurso	Configuração
CPU	2 vCPUs
Memória RAM	4 GB
Armazenamento	30 GB (VDI dinâmico)
Hostname	zabbix-server
Usuário administrativo	admin
Tipo de instalação	Não assistida

Essa configuração foi dimensionada para suportar:

Zabbix Server

MariaDB

Grafana

Zabbix Agent

em ambiente de laboratório com carga leve a moderada.
