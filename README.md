# main.py
from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes
import os

BOT_TOKEN = os.getenv("BOT_TOKEN")

async def bash_clown_bear(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("hi bear")

app = ApplicationBuilder().token(BOT_TOKEN).build()
app.add_handler(CommandHandler("bash.clown_bear", bash_clown_bear))

print("Bot is running...")
app.run_polling()