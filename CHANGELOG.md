# Changelog

All notable changes to Astradraw Room will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.2] - 2025-12-19

### Changed

- Ensured `maxHttpBufferSize` is consistently set to 200MB to support synchronized large image uploads.

## [0.1.0] - 2024-12-18

### Changed

- Increased `maxHttpBufferSize` to 200MB to support larger file transfers during collaboration
- Updated Node.js base image from 12 to 18 in Dockerfile
- Changed git remote to astrateam-net/astradraw-room

### Added

- New release workflow with GitHub Container Registry (GHCR) publishing
- Multi-platform Docker builds (amd64, arm64)
- Automatic GitHub releases with changelog extraction

### Removed

- Old Docker Hub publish workflow
