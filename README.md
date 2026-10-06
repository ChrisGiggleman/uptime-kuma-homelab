# Uptime Kuma Homelab

A hands-on monitoring and alerting lab deployed with Docker Compose on a Windows 11 / WSL2 homelab host.

## Project Goals
- Deploy Uptime Kuma v2 with Docker Compose
- Persist configuration and monitoring history
- Monitor key homelab services
- Detect service outages and recovery
- Send Discord DOWN and UP alerts
- Validate persistence after container recreation
- Verify resource usage and restart policy
- Document troubleshooting

## Lab Environment
| Component | Configuration |
|---|---|
| Host | GEEKOM Air12 Lite |
| OS | Windows 11 Pro |
| Docker backend | WSL2 |
| Host LAN IP | `192.168.0.181` |
| Uptime Kuma | v2.5.5 during validation |
| Image | `louislam/uptime-kuma:2` |
| Web UI | `http://192.168.0.181:3001` |
| Database | SQLite |
| Persistent data | `./data:/app/data` |
| Restart policy | `unless-stopped` |

> `192.168.0.181` is an RFC1918 private LAN address.

## Monitors
- AMP — `http://192.168.0.181:8080`
- Docker Nginx Test — `http://192.168.0.181:8081`
- GEEKOM Host — Ping `192.168.0.181`
- Nginx Proxy Manager — `http://192.168.0.181:81`

## Outage / Recovery Test
The Docker Nginx test stack was intentionally stopped. Kuma detected `ECONNREFUSED`, marked the service Down, and sent a Discord alert. After the service was restored, Kuma detected `200 - OK`, returned the monitor to Up, and sent a recovery alert.

## Persistence Test
Uptime Kuma itself was recreated with:

```powershell
cd C:\Docker-Lab\uptime-kuma
docker compose down
docker compose up -d
```

The admin account, monitors, history, and Discord notification configuration remained available.

## Final Resource Check
Observed:
- CPU: ~1.13%
- Memory: ~118.9 MiB
- Restart policy: `unless-stopped`

## Status
**Project 3 - Uptime Kuma: Complete**

Next planned homelab project: **Vaultwarden**
