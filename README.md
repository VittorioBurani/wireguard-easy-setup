# wireguard-easy-setup

Docker Compose file to setup `wg-easy` on a device on your LAN to setup WireGuard VPN easily.

## Configure

Copy the `.env.example` to `.env:

```bash
cp .env.example .env
```

Choose a password and run:

```bash
docker run --rm -it ghcr.io/wg-easy/wg-easy wgpw 'YOUR_CHOSEN_PASSWORD'
```

Save the returned hashed password to update your `.env` file:

```txt
WG_HOST="YOURNAME.duckdns.org"
PASSWORD_HASH="$$2a$$12$$..."
WG_PORT=51820
WG_DEFAULT_ADDRESS=10.8.0.x
WG_DEFAULT_DNS=""
```

- `WG_HOST`: public static IP or dynamic IP
- `PASSWORD_HASH`: the hashed password returned before
- `WG_PORT`: exposed port via UDP (default: 51820)

## Run

Simply run:

```bash
docker compuse up -d
```

Check logs with:

```bash
docker compose logs -f wg-easy    # Ctrl-C to exit logs
```
