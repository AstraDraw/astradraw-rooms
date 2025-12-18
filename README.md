# Astradraw Room

WebSocket collaboration server for [Astradraw](https://github.com/astrateam-net/astradraw), a self-hosted Excalidraw deployment.

This is a fork of [excalidraw/excalidraw-room](https://github.com/excalidraw/excalidraw-room) with modifications for Astradraw.

## Changes from upstream

- Increased `maxHttpBufferSize` to 200MB (from default 1MB) to support larger file transfers
- Updated Node.js to v18
- GitHub Container Registry (GHCR) publishing instead of Docker Hub
- Multi-platform Docker builds (amd64, arm64)

## Docker

```bash
docker pull ghcr.io/astrateam-net/astradraw-room:latest
```

## Environment Variables

| Variable      | Description         | Default                    |
| ------------- | ------------------- | -------------------------- |
| `PORT`        | Server port         | `80` (prod) / `3002` (dev) |
| `CORS_ORIGIN` | Allowed CORS origin | `*`                        |

## Development

### Install dependencies

```bash
yarn
```

### Run development server

```bash
yarn start:dev
```

## Production with PM2

If you need to use cluster mode with PM2, see: https://socket.io/docs/v4/pm2/

```bash
pm2 start pm2.production.json
```

## License

MIT
