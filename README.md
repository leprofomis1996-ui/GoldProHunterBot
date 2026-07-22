# GoldProHunterBot
GoldProHunterBot/
│
├── bot.py
from telegram import Update
from telegram.ext import (
    Application,
    CommandHandler,
    ContextTypes,
)

from config import BOT_TOKEN


async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        """
👋 Welcome to Gold Pro Hunter

📈 Gold Analysis
📊 US Stocks
📰 Economic News
🎓 ICT Academy
Educational purposes 
"""
    )

def main():
    app = Application.builder().token(BOT_TOKEN).build()

    app.add_handler(CommandHandler("start", start))

    print("Gold Pro Hunter is running...")

    app.run_polling()


if __name__ == "__main__":
    main()
├── config.py
import os

BOT_TOKEN = os.getenv("BOT_TOKEN")
├── requirements.txt
python-telegram-bot==21.4
python-dotenv==1.0.1
├── .gitignore
.env
__pycache__/
└── README.md
