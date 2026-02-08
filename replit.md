# Kezu MD - WhatsApp Bot

## Overview
A WhatsApp pairing bot built with Node.js and Express. It provides a web interface for users to pair their WhatsApp number with the bot using Baileys (WhatsApp Web API). The bot supports various features including auto status viewing, auto reactions, newsletter management, and command handling.

## Project Architecture
- **index.js** - Express server entry point, serves the frontend HTML pages and mounts the pairing API routes
- **pair.js** - Core bot logic: WhatsApp socket management, MongoDB session storage, command handlers, newsletter/status handlers
- **msg.js** - Message parsing utilities for Baileys
- **id.js** - Random ID generator utility
- **config.js** - Bot configuration (prefix, owner info, feature toggles)
- **main.html** - Frontend landing page with pairing terminal UI

## Key Dependencies
- **Express** - Web server (port 5000, bound to 0.0.0.0)
- **Baileys** (dew-coders fork) - WhatsApp Web API
- **MongoDB** - Session and configuration storage (external MongoDB Atlas)
- **fluent-ffmpeg** / **@ffmpeg-installer/ffmpeg** - Media processing
- **jimp** - Image manipulation
- **pino** - Logging

## Configuration
- Server runs on port 5000 (0.0.0.0)
- MongoDB connection configured via `MONGO_URI` environment variable (defaults to hardcoded Atlas URI)
- Owner number configurable via `OWNER_NUMBER` env var

## Recent Changes
- 2026-02-06: Upgraded from Node.js 18 to Node.js 20 (required by baileys dependency)
- 2026-02-06: Changed server port from 8000 to 5000 and bound to 0.0.0.0 for Replit compatibility
