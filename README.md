# 🟦 Desafio: Configuração de Banco de Dados na Azure

Este repositório documenta minha experiência prática no laboratório da DIO sobre **Configuração de uma Instância de Banco de Dados na Microsoft Azure**. Aqui você encontrará resumos, anotações, comandos e dicas úteis para auxiliar na criação, gerenciamento e conexão de bancos de dados em nuvem utilizando a plataforma Azure.

## 📌 Objetivo do Desafio

O principal objetivo deste laboratório foi aplicar, de forma prática, os conceitos aprendidos durante as aulas sobre computação em nuvem e serviços de banco de dados oferecidos pela Azure.

Além disso, este repositório foi criado como material de apoio para meus estudos futuros e também para compartilhar conhecimento com outros desenvolvedores.

## 🎯 O que aprendi

- Criação de uma conta gratuita na Azure.
- Provisionamento de um recurso de banco de dados relacional (Azure Database for MySQL / PostgreSQL / SQL Server).
- Configuração de firewall e regras de acesso à instância.
- Geração de strings de conexão seguras.
- Conexão com ferramentas externas como DBeaver, Azure Data Studio ou clientes SQL via terminal.
- Práticas recomendadas de segurança e organização na nuvem.

## 📝 Anotações e Comandos

### 🔧 Criando um recurso de Banco de Dados

```bash
# Exemplo com Azure CLI
az login
az group create --name meu-grupo --location eastus
az mysql flexible-server create --name meubancodados \
  --resource-group meu-grupo \
  --location eastus \
  --admin-user adminuser \
  --admin-password MinhaSenhaSegura123 \
  --sku-name Standard_B1ms \
  --storage-size 20
```

### 🔐 Configurando regras de firewall

```bash
az mysql flexible-server firewall-rule create \
  --resource-group meu-grupo \
  --name meubancodados \
  --rule-name allow-local \
  --start-ip-address 0.0.0.0 \
  --end-ip-address 0.0.0.0
```

### 🌐 Conectando ao Banco

- Use um cliente gráfico como DBeaver ou Azure Data Studio.
- Conecte-se usando o host, usuário e senha definidos na criação.
- Verifique a string de conexão nos detalhes da instância no portal da Azure.
 
### 💡 Dicas Úteis

- Use grupos de recursos para manter seus serviços organizados.
- Configure variáveis de ambiente locais para armazenar senhas e evitar exposição em scripts.
- Explore o Azure Cost Management para acompanhar seu consumo gratuito.
- Ative alertas de orçamento para evitar custos inesperados.

### ✅ Conclusão

Esse desafio me proporcionou uma visão prática sobre como utilizar os recursos de banco de dados da Azure, desde a criação até a conexão e boas práticas de segurança. Utilizar o GitHub para documentar essa experiência torna mais fácil revisitar o conteúdo futuramente e compartilhar conhecimento com outros desenvolvedores.
