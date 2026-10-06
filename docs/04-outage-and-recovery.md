# 04 - Outage and Recovery

The Docker Nginx test stack was intentionally stopped:

```powershell
cd C:\Docker-Lab\nginx-test
docker compose down
```

Kuma detected:

```text
connect ECONNREFUSED 192.168.0.181:8081
```

After:

```powershell
docker compose up -d
```

Kuma detected `200 - OK` and returned the service to Up.
