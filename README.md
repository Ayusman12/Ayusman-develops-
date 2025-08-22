# Telegram Bot Starter (python-telegram-bot + Docker)

A minimal Telegram bot ready for deployment as a **background worker** (long polling).

## Local run

1. Create a virtual environment (optional) and install deps:
   ```bash
   pip install -r requirements.txt
   ```
2. Set your token:
   ```bash
   export BOT_TOKEN=123456:ABC-YourTokenHere
   ```
3. Run:
   ```bash
   python bot.py
   ```

## Deploy on Railway (recommended)

1. Create a new **private** GitHub repo and upload these files.
2. Go to [Railway](https://railway.app/) → sign in with GitHub.
3. **New Project** → **Deploy from GitHub repo** → select your repo.
4. When Railway asks for the service type, choose **Worker** (not Web Service).
5. In **Variables**, add `BOT_TOKEN` with the token you got from BotFather.
6. Deploy. Check **Logs** to see “Application started” — your bot is live.
7. Open Telegram and send `/start` to your bot.

> If you prefer **Render**: create a **Background Worker** from your repo and set the start command to `python bot.py` with `BOT_TOKEN` in the environment.

## Next: add real intelligence

- Replace the `echo` handler with your logic (APIs, database, LLMs, etc.).
- Add more commands:
  ```python
  app.add_handler(CommandHandler("about", about_handler))
  ```
