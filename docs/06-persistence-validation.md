# 06 - Persistence Validation

Uptime Kuma was removed and recreated:

```powershell
cd C:\Docker-Lab\uptime-kuma
docker compose down
docker compose up -d
```

The admin account, four monitors, event history, and Discord notification configuration survived, validating the persistent bind mount `./data:/app/data`.
