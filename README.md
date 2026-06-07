# 🐳 pma-docker

> Simple **MariaDB** + **phpMyAdmin** + **Nginx (SSL)** stack running in Docker.

[![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)](https://www.docker.com/)
[![MariaDB](https://img.shields.io/badge/MariaDB-003545?logo=mariadb&logoColor=white)](https://mariadb.org/)
[![Nginx](https://img.shields.io/badge/Nginx-009639?logo=nginx&logoColor=white)](https://nginx.org/)

---

## 📦 Stack

| Service | Description |
| :--- | :--- |
| **MariaDB** | Database engine |
| **phpMyAdmin** | Web UI for database management |
| **Nginx** | Reverse proxy with SSL support |

---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone <repo-url>
cd pma-docker

# 2. Create your .env file and set MARIADB_ROOT_PASSWORD
cp .env.example .env

# 3. Start the containers
docker compose up -d
```

✅ Ready! Access phpMyAdmin at **http://localhost:6001**

---

## 🔒 Optional: Nginx + SSL (Cloudflare)

```bash
# 1. Install Nginx
sudo apt install nginx

# 2. Paste your Cloudflare certs into:
#    ssl/cert.pem  &  ssl/key.pem

# 3. Replace the domain in nginx.conf

# 4. Copy the Nginx config
sudo cp nginx.conf /etc/nginx/conf.d/pma.conf

# 5. Copy the SSL certs
sudo mkdir -p /etc/ssl/webs && sudo cp -r ssl /etc/ssl/webs/pma

# 6. Restart Nginx
sudo systemctl restart nginx
```

---

## 📝 Environment Variables

| Variable | Description | Required |
| :--- | :--- | :---: |
| `MARIADB_ROOT_PASSWORD` | Root password for MariaDB | ✅ |

---

## 📄 License

Feel free to use and modify.