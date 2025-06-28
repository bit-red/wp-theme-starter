# WordPress Theme Development Starter

🚀 Template profissional para desenvolvimento de temas WordPress com Docker.

## ⚡ Instalação rápida

```bash
composer create-project bit-red/wp-theme-starter meu-projeto
cd meu-projeto
```

**Pronto!** O WordPress estará rodando em http://localhost:8080

## 📋 O que é configurado automaticamente

✅ **WordPress** com Docker  
✅ **MariaDB** como banco de dados  
✅ **Volumes montados** para desenvolvimento local  
✅ **Arquivo .env** criado e configurado  
✅ **Estrutura de pastas** para temas e plugins  
✅ **Auto-detecção** de primeira execução

## 🎯 Acesso rápido

- **Site:** http://localhost:8080
- **Admin:** http://localhost:8080/wp-admin
    - **Usuário:** `admin`
    - **Senha:** `admin123`

## 🛠️ Comandos disponíveis

```bash
# Gerenciar containers
composer run dev        # Iniciar WordPress
composer run stop       # Parar containers  
composer run restart    # Reiniciar containers
composer run logs       # Ver logs em tempo real
composer run clean      # Limpar tudo e recomeçar

# Desenvolvimento
composer run shell      # Entrar no container WordPress
```

## 📁 Estrutura do projeto

```
meu-projeto/
├── themes/              # 📁 Seus temas personalizados
├── plugins/             # 🔌 Seus plugins personalizados
├── uploads/             # 📂 Arquivos de upload
├── docker-compose.yml   # 🐳 Configuração Docker
├── .env                 # ⚙️ Variáveis de ambiente
└── composer.json        # 📦 Configuração Composer
```

## ⚙️ Personalização

### Alterar portas ou credenciais
Edite o arquivo `.env`:
```bash
# Portas
HOST_HTTP_PORT=8080
HOST_HTTPS_PORT=8443

# Credenciais admin
WORDPRESS_USERNAME=admin
WORDPRESS_PASSWORD=suaSenhaSegura

# Banco de dados
MARIADB_PASSWORD=senhaDoDb
```

Depois reinicie:
```bash
composer run restart
```
---

**Criado para acelerar o desenvolvimento de temas WordPress**