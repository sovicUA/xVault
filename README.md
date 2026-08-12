# Vaultwarden Docker Project

This project provides a minimal and production-oriented Docker setup for Vaultwarden.

## 1) Prerequisites

- Docker Desktop (Windows) or Docker Engine + Docker Compose plugin

## 2) Initial setup

1. Copy `.env.example` to `.env`.
2. Set a strong `ADMIN_TOKEN` value.
3. (Optional) Update `DOMAIN` to your real HTTPS URL.

PowerShell example:

```powershell
Copy-Item .env.example .env
```

## 3) Start service

```powershell
docker compose up -d
```

Check status:

```powershell
docker compose ps
```

## 4) Access

- User portal: http://localhost:8080
- Admin portal: http://localhost:8080/admin

## 5) Stop service

```powershell
docker compose down
```

## 6) Update Vaultwarden

```powershell
docker compose pull
docker compose up -d
```

## 7) Backup

Back up the `data` folder regularly. It contains the SQLite database and attachments.

## Security notes

- Keep `.env` private.
- Do not expose the admin panel publicly without additional protection.
- For internet exposure, run behind HTTPS reverse proxy (Nginx/Caddy/Traefik).
