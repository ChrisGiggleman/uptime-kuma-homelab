# 07 - Final Validation

Final checks:

```powershell
docker compose ps
docker stats --no-stream uptime-kuma
docker inspect uptime-kuma --format '{{.HostConfig.RestartPolicy.Name}}'
```

Observed approximately:
- CPU: 1.13%
- Memory: 118.9 MiB
- Restart policy: `unless-stopped`

**Project status: Complete**
