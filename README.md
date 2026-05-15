# limits free bot — Railway ready

This package keeps `/freelink`. Users do **not** need to paste their token every time they run `/freemines`.

Important: there is **no persistent database** in this version. Linked Bloxflip tokens are kept only in process RAM. They are never written to a file, SQLite database, or external database. This means:

- Users stay linked while the bot process is running.
- If Railway restarts/redeploys the bot, RAM is cleared and users must run `/freelink` again.
- `/freeunlink` lets a user remove their token from RAM manually.

## Files

- `main.py` — bot source code
- `requirements.txt` — dependencies for Railway/Railpack
- `Procfile` — start command for worker process
- `railway.json` — Railway start command
- `.python-version` — Python version hint
- `.gitignore` — ignores env/log/cache files

## Railway variables

Add these in Railway → Variables:

```env
BOT_TOKEN=your_discord_bot_token
ALLOWED_CHANNEL_ID=your_predict_channel_id
ANNOUNCEMENT_CHANNEL_ID=your_announcement_channel_id
OWNER_ID=your_discord_user_id
```

## Start command

The package already includes this, but if Railway asks for it manually:

```bash
python main.py
```

## Commands

- `/freelink token` — link Bloxflip token into RAM-only session
- `/setmethod` — choose prediction method
- `/freemines` — predict using linked token
- `/freeunlink` — remove linked token from RAM
- `/maintenancestart` — owner only
- `/maintenanceend` — owner only
