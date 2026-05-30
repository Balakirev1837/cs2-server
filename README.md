# CS2 Dedicated Server

Counter-Strike 2 dedicated server using [joedwards32/cs2](https://github.com/joedwards32/CS2) Docker image.

## Setup

1. Copy `.env.example` to `.env` and set your `SRCDS_TOKEN`:
   ```bash
   cp .env.example .env
   # Edit .env and add your Steam Game Server Token
   # Get one at https://steamcommunity.com/dev/managegameservers
   ```

2. Start the server:
   ```bash
   docker compose up -d
   ```

3. Check logs:
   ```bash
   docker compose logs -f cs2
   ```

## Requirements

- 2+ CPUs, 2GB+ RAM, 60GB+ disk space
- Steam Game Server Token ([get one here](https://steamcommunity.com/dev/managegameservers))

## Configuration

All settings are environment variables in `docker-compose.yml`. Key settings:

| Variable | Default | Description |
|---|---|---|
| `SRCDS_TOKEN` | (required) | Steam Game Server Token |
| `CS2_SERVERNAME` | `changeme` | Server name in browser |
| `CS2_RCONPW` | `dateniteroolz` | RCON password |
| `CS2_MAXPLAYERS` | `10` | Max players |
| `CS2_GAMEALIAS` | (empty) | Game mode alias (casual, competitive, deathmatch) |
| `CS2_STARTMAP` | `de_inferno` | Starting map |

See the [upstream README](https://github.com/joedwards32/CS2) for full configuration options.

## Game Updates

Restart the container to apply game updates:
```bash
docker compose restart cs2
```

The container auto-updates on startup.
