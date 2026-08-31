# Telegram Keyword Replacer (Global)

Universal keyword replacement bot for Telegram channels.

## Features

- **Global keywords** — one rule set for all chats
- Owner + authorized admins can manage rules
- Text & caption in-place edit
- PDF/document filename rename (ordered re-upload)
- Broadcast to users who `/start`ed the bot
- Render free Web Service ready

## Render Environment

| Key | Value |
|-----|--------|
| `BOT_TOKEN` | From @BotFather |
| `OWNER_ID` | Your numeric Telegram ID |
| `DATABASE_URL` | `sqlite+aiosqlite:///./bot.db` **or** `postgresql+asyncpg://user:pass@host:5432/db?ssl=require` |
| `PYTHON_VERSION` | `3.12.7` |
| `LOG_LEVEL` | `INFO` |

**Build:** `pip install -r requirements.txt`  
**Start:** `python -m bot.main`  
**Type:** Web Service (Free)

## Commands

### Owner & Admins
`/addkeyword OLD | NEW` · `/deletekeyword OLD` · `/listkeywords` · `/clearkeywords`  
`/enable` · `/disable` · `/status` · `/panel`

### Owner only
`/addadmin ID` · `/removeadmin ID` · `/listadmins`  
`/users` · `/broadcast message`

### Anyone
`/start` · `/myid` · `/help`

## Notes

- Prefer **Channels** (bot as admin with post + delete)
- Password `#` in DB URL → `%23`
- Postgres: use `postgresql+asyncpg://` (not psycopg2, not mongodb)
- Only **one** bot instance per token (no Conflict error)

MIT License
