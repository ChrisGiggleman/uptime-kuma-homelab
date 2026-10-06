# 01 - Deployment

Created `C:\Docker-Lab\uptime-kuma` and deployed Uptime Kuma with Docker Compose.

The initial `louislam/uptime-kuma:1` image was replaced with `louislam/uptime-kuma:2` after the UI warned that v1 was outdated.

Validation commands:

```powershell
docker compose config
docker compose pull
docker compose up -d
docker compose ps
docker compose logs --tail 50
```
