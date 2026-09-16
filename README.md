# 🐉 DRACO — Moderation Unleashed

**All-in-one Discord moderation bot with 1000+ commands, FastAPI backend, and web dashboard.**

## Features

- ✨ **1000+ Commands** across 30+ modules (slash + prefix hybrid)
- 🛡️ **AutoMod** — 30+ anti-abuse modules (nuke, spam, raid, links, etc.)
- 🎵 **Music** — Wavelink 3.x integration with Lavalink
- 🔊 **Voice Master** — Join-to-create channels with owner controls
- 💰 **Economy** — Full currency system with shops, banks, and trading
- 📈 **Leveling** — Customizable XP system with role rewards
- 🎉 **Giveaways** — Interactive button-based giveaway system
- 🎫 **Tickets** — Support ticket system with transcripts
- 🌐 **Web Dashboard** — Beautiful Next.js UI for guild configuration
- ⚡ **FastAPI Backend** — Real-time sync between bot and web
- 📊 **SQLite Persistence** — Per-guild settings with audit logs
- 🔐 **OAuth2 Authentication** — Discord login integration

## Project Structure

```
draco-bot/
├── bot.py                  # Discord bot entry point
├── config.py              # Configuration & constants
├── database.py            # SQLite wrapper with aiosqlite
├── requirements.txt
├── Procfile
├── runtime.txt
├── railway.json
├── .env.example
├── README.md
├── cogs/                  # Modular command cogs (30+)
│   ├── moderation.py
│   ├── automod.py
│   ├── music.py
│   ├── voice.py
│   ├── economy.py
│   ├── leveling.py
│   └── ... (25+ more)
├── utils/
│   ├── embeds.py          # Embed builders with theme
│   ├── checks.py          # Permission decorators
│   ├── helpers.py         # Utilities
│   └── views.py           # UI components
├── api/                   # FastAPI backend
│   ├── main.py
│   ├── models.py
│   ├── routes/
│   │   ├── auth.py
│   │   ├── bot.py
│   │   ├── guilds.py
│   │   └── config.py
│   └── ...
└── web/                   # Next.js dashboard (separate repo)
```

## Setup

### Prerequisites
- Python 3.11+
- Node.js 18+ (for web dashboard)
- Discord bot token
- Lavalink server (optional, for music)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/anx6ty/draco-bot.git
   cd draco-bot
   ```

2. **Create virtual environment**
   ```bash
   python3.11 -m venv venv
   source venv/bin/activate  # or `venv\Scripts\activate` on Windows
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Setup environment**
   ```bash
   cp .env.example .env
   # Edit .env with your Discord token and other secrets
   ```

5. **Run the bot**
   ```bash
   python bot.py
   ```

## Deployment

### Railway

1. Create a new Railway project
2. Connect your GitHub repository
3. Add environment variables from `.env.example`
4. Deploy! Both web and worker services auto-start.

### Docker

```bash
docker build -t draco-bot .
docker run -d --env-file .env draco-bot
```

## Configuration

Use `/config` in Discord to open the interactive configuration panel:

1. Select a module category (Moderation, AutoMod, Music, etc.)
2. Click buttons to edit settings
3. Changes sync instantly to the database
4. All edits logged in the audit feed

Or visit the **web dashboard** at `https://your-instance.railway.app/dashboard` to configure everything from a browser.

## Commands

Over 1000 commands across these categories:

- **Moderation** (150+) — ban, kick, mute, warn, purge, slowmode, etc.
- **AutoMod** (80+) — anti-nuke, anti-spam, anti-raid, anti-link, etc.
- **Music** (45+) — play, skip, queue, lyrics, filters, playlists
- **Voice** (25+) — join-to-create, channel controls, permissions
- **Economy** (60+) — balance, shop, bank, trading, gambling
- **Leveling** (25+) — experience, ranks, role rewards, streaks
- **Fun** (120+) — games, memes, images, polls, trivia
- **Utility** (100+) — info, search, converters, reminder, todos
- **... and 25+ more modules**

Use `/commands` or `/help` to browse all available commands.

## API Endpoints

### Bot Sync
```
GET /api/bot/guilds/{guild_id}/sync
```
Returns guild configuration for the bot to use at runtime.

### Guild Management
```
GET  /api/guilds
POST /api/guilds/{guild_id}/config
PUT  /api/guilds/{guild_id}/config
```

### Audit Logs
```
GET /api/guilds/{guild_id}/audit
```

## Contributing

Contributions welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## License

MIT License — see LICENSE file for details.

## Support

For issues, questions, or suggestions:
- 🐛 Open an issue on GitHub
- 💬 Join our Discord server
- 📧 Email: support@dracobot.dev

---

**Made with 🔥 by the Draco team**