# 📐 Architecture Overview

## Network

All services run on a Docker bridge network called `network-bridge`.

## Components

- **Confluence** runs on port `8090` internally
- **MySQL** as DB backend with utf8mb4 encoding
- **Nginx** acts as reverse proxy and TLS terminator
