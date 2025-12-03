# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an Umbrel Community App Store that distributes the **Igloo Server** application. Igloo Server is a multi-user FROSTR signing server with a persistent relay for Nostr.

## Repository Structure

- `umbrel-app-store.yml` - App store configuration (ID: `igloo`, name: "Igloo Server Store")
- `igloo-server/` - The app package directory
  - `umbrel-app.yml` - App metadata and listing details shown in Umbrel UI
  - `docker-compose.yml` - Docker service configuration
  - `assets/` - App icon and gallery images

## Key Configuration Files

### umbrel-app-store.yml
Defines the app store ID (`igloo`) and display name. The app store ID is used as a prefix for all app IDs.

### igloo-server/umbrel-app.yml
Contains app metadata: name, version, description, icon URL, gallery images, and dependencies.

### igloo-server/docker-compose.yml
Defines two services:
- `igloo` - The main Igloo Server container (from `ghcr.io/frostr-org/igloo-server:umbrel-dev`)
- `app_proxy` - Umbrel's proxy service for routing traffic

## Conventions

- App IDs must be prefixed with the store ID (e.g., `igloo-server` for store ID `igloo`)
- The app folder name must match the app ID in `umbrel-app.yml`
- Environment variables like `${APP_PASSWORD}` and `${APP_DATA_DIR}` are provided by Umbrel at runtime
