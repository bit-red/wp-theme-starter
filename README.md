# WordPress Theme Development Starter

🚀 Template profissional para desenvolvimento de temas WordPress com Docker.

## ⚡ Instalação rápida

```bash
composer create-project bit-red/wp-theme-starter meu-projeto
cd meu-projeto

# Copiar arquivo de configuração
cp .env.example .env

# Ou no Windows:
copy .env.example .env

# Iniciar WordPress
docker-compose up -d
```

**Pronto!** O WordPress estará rodando em http://localhost:8080

## 🎯 Acesso rápido

- **Site:** http://localhost:8080
- **Admin:** http://localhost:8080/wp-admin
    - **Usuário:** `admin`
    - **Senha:** `admin123`

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

## 🔧 Desenvolvimento de Temas, Plugins e Upload de Arquivos

Se você deseja criar temas/plugins personalizados ou ter acesso aos arquivos de upload, após subir o ambiente Docker, você precisa:

### 1. Copiar os arquivos do container para o host:

```bash
docker cp wordpress_app:/bitnami/wordpress/wp-content/themes/. ./themes/
docker cp wordpress_app:/bitnami/wordpress/wp-content/plugins/. ./plugins/
docker cp wordpress_app:/bitnami/wordpress/wp-content/uploads/. ./uploads/
```

### 2. Descomentar as linhas de volume no `docker-compose.yml`:

```yaml
volumes:
  - 'wordpress_data:/bitnami/wordpress'
  - './themes:/bitnami/wordpress/wp-content/themes'
  - './plugins:/bitnami/wordpress/wp-content/plugins'
  - './uploads:/bitnami/wordpress/wp-content/uploads'
```

### 3. Reiniciar o container:

```bash
docker-compose down
docker-compose up -d
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