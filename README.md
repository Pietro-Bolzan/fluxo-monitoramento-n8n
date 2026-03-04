# 🚨 Sistema Inteligente de Monitoramento com n8n

Este projeto é uma automação de monitoramento ativo de serviços (Health Check) construída em **n8n**. O sistema verifica periodicamente a disponibilidade de uma API/Servidor, registra o histórico em um banco de dados relacional (**PostgreSQL** via Docker) e escala alertas críticos para a equipe de infraestrutura via **Discord Webhook** em caso de falhas (Downtime).

## 🛠️ Arquitetura e Tecnologias
* **Orquestração:** n8n (Node-based Workflow Automation)
* **Banco de Dados:** PostgreSQL (Rodando em container Docker local)
* **Notificações:** Integração via Webhook nativo do Discord
* **Lógica de Negócio:** Tratamento de erros HTTP, condicionais lógicas (IF) e manipulação de JSON.

## 🚀 Como replicar este ambiente

### 1. Subindo o Banco de Dados
O banco de dados foi provisionado utilizando Docker. Para iniciar o container, execute:
```bash
docker run --name log-db -e POSTGRES_PASSWORD=sua_senha -p 5432:5432 -d postgres
