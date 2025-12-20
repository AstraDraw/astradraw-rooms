# AstraDraw Room

WebSocket collaboration server for [AstraDraw](https://github.com/astrateam-net/astradraw), a self-hosted Excalidraw deployment.

This is a fork of [excalidraw/excalidraw-room](https://github.com/excalidraw/excalidraw-room) with modifications for AstraDraw.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE) [![Docker](https://img.shields.io/badge/docker-ghcr.io-blue)](https://github.com/astrateam-net/astradraw-room/pkgs/container/astradraw-room)

## Changes from Upstream

- Increased `maxHttpBufferSize` to 200MB (from default 1MB) to support larger file transfers
- Updated Node.js to v18
- GitHub Container Registry (GHCR) publishing
- Multi-platform Docker builds (amd64, arm64)

## Architecture

This is the WebSocket component of the AstraDraw suite:

- **[astradraw-app](https://github.com/astrateam-net/astradraw-app)**: Frontend application
- **[astradraw-api](https://github.com/astrateam-net/astradraw-api)**: Backend API
- **astradraw-room** (this repo): WebSocket collaboration server
- **[astradraw](https://github.com/astrateam-net/astradraw)**: Deployment configuration & documentation

## Quick Start

### Using Docker (Production)

```bash
docker pull ghcr.io/astrateam-net/astradraw-room:latest

docker run -d \
  -p 80:80 \
  -e PORT=80 \
  -e CORS_ORIGIN=* \
  ghcr.io/astrateam-net/astradraw-room:latest
```

### Local Development

```bash
# Install dependencies
yarn install

# Start dev server
yarn start:dev

# Run checks before committing
yarn build    # TypeScript compilation
yarn test     # Prettier + ESLint check
yarn fix      # Auto-fix issues
```

## Environment Variables

| Variable      | Description         | Default                    |
| ------------- | ------------------- | -------------------------- |
| `PORT`        | Server port         | `80` (prod) / `3002` (dev) |
| `CORS_ORIGIN` | Allowed CORS origin | `*`                        |
| `DEBUG`       | Debug logging       | -                          |

## Production with PM2

If you need to use cluster mode with PM2, see: https://socket.io/docs/v4/pm2/

```bash
pm2 start pm2.production.json
```

## Deployment

For complete deployment with frontend, backend API, and Traefik proxy, see the [astradraw deployment repo](https://github.com/astrateam-net/astradraw).

## License

MIT License - Based on [excalidraw-room](https://github.com/excalidraw/excalidraw-room)

## Links

- **Main Repo**: [astradraw](https://github.com/astrateam-net/astradraw)
- **Frontend App**: [astradraw-app](https://github.com/astrateam-net/astradraw-app)
- **Backend API**: [astradraw-api](https://github.com/astrateam-net/astradraw-api)
- **Upstream**: [excalidraw/excalidraw-room](https://github.com/excalidraw/excalidraw-room)
- **Docker Image**: [ghcr.io/astrateam-net/astradraw-room](https://github.com/astrateam-net/astradraw-room/pkgs/container/astradraw-room)
