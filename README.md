# HRP-Authentication Project

## Overview
HRP-Authentication is a complete authentication system for FiveM/QBCore featuring Discord OAuth, QR code login, anti-alt detection, and admin whitelisting.

## Features
- ✓ Discord Authentication
- ✓ QR Code Login
- ✓ NUI Interface
- ✓ Anti-Alt System
- ✓ Session Management
- ✓ Permanent User Identification
- ✓ Admin Whitelist
- ✓ Blacklist System
- ✓ txAdmin Integration

## Project Structure
```
HRP-Authentication/
├── fxmanifest.lua          # FiveM resource manifest
├── config.lua              # Configuration file
├── server/                 # Server-side Lua scripts
│   ├── main.lua           # Main server handler
│   ├── auth.lua           # Authentication logic
│   ├── sessions.lua       # Session management
│   ├── whitelist.lua      # Whitelist system
│   ├── blacklist.lua      # Blacklist system
│   ├── anti_alt.lua       # Anti-alt detection
│   ├── txadmin.lua        # txAdmin integration
│   └── database.lua       # Database operations
├── client/                 # Client-side Lua scripts
│   ├── main.lua           # Main client handler
│   ├── nui.lua            # NUI communication
│   └── camera.lua         # Authentication camera
├── web/                    # NUI Web Interface
│   ├── index.html         # Main HTML
│   ├── style.css          # Styling
│   ├── app.js             # Frontend logic
│   └── assets/            # Images and assets
├── backend/                # Node.js Backend
│   ├── server.js          # Express server
│   ├── package.json       # Node dependencies
│   └── routes/            # API routes
└── sql/                    # Database schema
    └── hrp_authentication.sql
```

## Installation

### 1. FiveM Resource Setup
1. Place the resource in your `resources` folder
2. Add to server.cfg: `ensure hrp-authentication`
3. Update `config.lua` with your Discord Guild ID and Role ID

### 2. Database Setup
1. Import `sql/hrp_authentication.sql` into your database
2. Update database credentials in `config.lua`

### 3. Backend Setup
```bash
cd backend
npm install
npm start
```

### 4. Configuration
Edit `config.lua`:
```lua
Config.DiscordGuild = 'YOUR_GUILD_ID'
Config.RequiredRole = 'YOUR_ROLE_ID'
Config.Webhooks = {
    Connections = 'YOUR_CONNECTION_WEBHOOK',
    Security = 'YOUR_SECURITY_WEBHOOK',
    Staff = 'YOUR_STAFF_WEBHOOK'
}
```

## Admin Commands
- `/hrp_whitelist [discord_id]` - Whitelist a player
- `/hrp_blacklist [discord_id] [reason]` - Blacklist a player
- `/hrp_lookup [discord_id]` - Look up player info

## Security Features
- Secure token generation (64-char random)
- Session expiration (configurable)
- IP hashing for anti-alt detection
- Device fingerprinting
- Replay protection
- Webhook logging

## Discord Integration
Requires Discord Bot with scopes:
- `applications.commands`
- `bot`
- `identify`
- `guilds`
- `guilds.members.read`

## Dependencies
### FiveM
- oxmysql
- ox_lib
- qb-core

### Backend
- express
- discord.js
- qrcode
- jsonwebtoken

## Debug Mode
Set `Config.Debug = true` in `config.lua` for detailed console logging.

## Support
For issues or questions, contact General Mokhtari

---
**Author:** General Mokhtari  
**Version:** 1.0.0  
**License:** MIT
