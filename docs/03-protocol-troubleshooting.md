# 03 - Protocol Troubleshooting

Initial HTTPS configuration against HTTP-only services caused:

```text
EPROTO
wrong version number
```

A malformed Docker Nginx monitor produced:

```text
getaddrinfo ENOTFOUND http
```

The Dragonwilds game server was tested on port 7778. TCP failed while UDP was listening, so the TCP Kuma monitor was removed to avoid a false Down state.
