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

---

## Criação da DATABASE ZABBIX

Seguindo a recomendação que pode ser encontrada na documentação do Zabbix 

primeiro utilizamos o comando para acessar o banco de dados

```bash
sudo mariadb
```
A criação foi realizada utilizando as configurações recomendadas oficialmente pelo Zabbix para garantir compatibilidade e integridade dos dados.

```bash
CREATE DATABASE zabbix
CHARACTER SET utf8mb4
COLLATE utf8mb4_bin;
```

CREATE DATABASE zabbix

Cria um banco de dados chamado zabbix, que será utilizado exclusivamente pelo servidor de monitoramento.

A separação do banco de dados garante:

Organização dos dados

Isolamento lógico

Melhor controle de permissões

Facilidade de backup e manutenção

CHARACTER SET utf8mb4

Define o conjunto de caracteres como utf8mb4.

O utf8mb4 é uma implementação completa do padrão UTF-8 e permite o armazenamento de:

Caracteres especiais

Acentuação

Símbolos

Emojis

Caracteres internacionais

Isso evita problemas de codificação e incompatibilidade em ambientes que utilizam múltiplos idiomas ou caracteres especiais.

COLLATE utf8mb4_bin

Define a regra de comparação de caracteres (collation).

A opção utf8mb4_bin realiza comparação binária, ou seja:

Sensível a maiúsculas e minúsculas

Comparação exata de caracteres

Maior precisão na diferenciação de strings

Essa configuração é recomendada pelo Zabbix para evitar inconsistências em:

Nomes de hosts

Identificadores de itens

Triggers

Chaves de monitoramento
