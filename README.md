# 🧠 Self-Hosted Confluence Deployment

A Docker-based deployment of Atlassian Confluence using MySQL and Nginx with HTTPS support.

---

## 🧰 Components

| Component     | Version  | Description                              |
|---------------|----------|------------------------------------------|
| Confluence    | 9.2.1    | Knowledge management platform             |
| MySQL         | 8.0      | Database backend for Confluence           |
| Nginx         | latest   | Reverse proxy with TLS termination        |
| Docker Compose| 3.4+     | Multi-container orchestration             |

---

## 📦 Clone the Project

```bash
git clone https://github.com/amiirsadeghi/Confluence.git

---

## ⚙️ Setup Instructions

### 1. Create Required Folders

```bash
mkdir -p ./data/confluence ./data/mysql
```

These directories will hold persistent data for Confluence and MySQL.

### 2. Prepare Environment Variables

Copy the sample file and edit as needed:

```bash
cp .env.example .env
nano .env
```

Ensure variables such as `MYSQL_PASSWORD`, `MYSQL_DATABASE`, and `TZ` are correctly set.

### 3. Provide SSL Certificates

Add your certificates to the `nginx/ssl/` folder:

```
nginx/
├── ssl/
│   ├── fullchain.pem   # Your SSL certificate
│   └── privkey.pem     # Your private key
```

> You can get free certificates from [Let's Encrypt](https://letsencrypt.org/) using Certbot.

---

## 🚀 Launch Environment

```bash
docker compose up -d
```

Check logs to ensure everything is running:

```bash
docker compose logs -f
```

Then access Confluence in your browser:

```
https://your-domain.com
```

---

## 🧪 Useful Commands

| Command                         | Description                    |
|---------------------------------|--------------------------------|
| `docker compose up -d`         | Start services                 |
| `docker compose down`          | Stop services                  |
| `docker compose ps`            | List running containers        |
| `docker compose logs -f`       | Tail logs                      |

---

## 📂 Project Structure

```
.
├── docker-compose.yml
├── .env.example
├── .gitignore
├── README.md
├── nginx/
│   ├── nginx.conf
│   └── ssl/
├── data/
│   ├── confluence/
│   └── mysql/
└── docs/
    └── architecture.md
```

---

## 🛠 Tips

- Make sure port 80 and 443 are open on your server.
- Use a valid domain (e.g. conf.etadbir.com) that points to the host IP.
- Use `docker volume` instead of local paths if running on remote systems.

---

## 📄 License

This project is for educational and internal use only.
No proprietary software or binaries are included in this repository.


