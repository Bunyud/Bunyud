from telegram.ext import Updater, CommandHandler, MessageHandler, Filters

# Bot tokenini kiriting
TOKEN = 6798291892:AAE6Dqq48zuBMxuDVoTnHCQZGScMnGQfo9o
'YOUR_BOT_TOKEN_HERE'

# Start komandasi uchun funksiya
def start(update, context):
    update.message.reply_text('Assalomu alaykum! Men botman.')

# Xabarlar uchun funksiya
def echo(update, context):
    update.message.reply_text(update.message.text)

# Asosiy funksiya
def main():
    updater = Updater(TOKEN, use_context=True)
    dp = updater.dispatcher

    dp.add_handler(CommandHandler("start", start))
    dp.add_handler(MessageHandler(Filters.text & ~Filters.command, echo))

    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main() 
    python bot.py
