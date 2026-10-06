# Lessons Learned

- Use the maintained Uptime Kuma v2 image rather than the deprecated v1 tag.
- Match monitor protocol to the actual service; using HTTPS against HTTP produced `EPROTO` errors.
- `ENOTFOUND`, `EPROTO`, and `ECONNREFUSED` indicate different failure classes and are useful for troubleshooting.
- TCP monitoring is not appropriate for a UDP-only service such as the tested Dragonwilds endpoint.
- Intentional outage testing proves monitoring behavior more effectively than installation alone.
- Discord webhook alerts provide actionable DOWN and recovery notifications.
- The `./data:/app/data` bind mount successfully preserved monitors, history, and settings.
- Uptime Kuma fits comfortably on the current GEEKOM host at roughly 119 MiB RAM during final validation.
