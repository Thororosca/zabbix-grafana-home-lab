# Banco de Dados – MariaDB

## Visão Geral
Neste projeto é utilizado o banco de dados relacional **:contentReference[oaicite:0]{index=0}**, responsável pelo armazenamento persistente das informações coletadas pelo **:contentReference[oaicite:1]{index=1}**, incluindo métricas, eventos, configurações, usuários e histórico de monitoramento.

O banco de dados é o primeiro componente a ser instalado, garantindo que a camada de persistência esteja disponível antes da implantação do Zabbix Server.

---

## Justificativa da escolha
O MariaDB foi adotado por apresentar:
- Alta compatibilidade com o Zabbix
- Estabilidade e desempenho adequados para ambientes de monitoramento
- Facilidade de administração e manutenção

---

## Ordem de implantação
A instalação do banco de dados antecede a instalação do Zabbix Server para assegurar que:
- O schema do Zabbix possa ser criado corretamente
- O serviço de banco de dados esteja operacional durante a configuração do Zabbix
- Não ocorram falhas de dependência durante a implantação

---

## Instalação do MariaDB

```bash
sudo apt install mariadb-server -y 
```
---

## Verificação da instalação do MariaDB

Após a instalação, o serviço do banco de dados foi validado através do systemd:

```bash
mariadb --version
```

---

## A verificação do serviço do MariaDB confirmou a instalação da versão **10.11.14**, conforme identificado no retorno do comando `mariadb --version`.
