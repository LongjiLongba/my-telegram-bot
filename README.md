import telebot
from telebot.types import InlineKeyboardMarkup, InlineKeyboardButton

TOKEN = '9237071248:AAHaWLCD6oot7yAhoME6yxErngghiM7C71k'
bot = telebot.TeleBot(TOKEN)

@bot.message_handler(commands=['start'])
def send_welcome(message):
    welcome_text = (
        "🐐🐐GOAT SERVICE DIRECTORY 🤩🐐\n\n"
        "✅Official Channels & Chats: ✅\n\n"
        "Tap any button below to open directly!"
    )
    
    # Create the button layout
    markup = InlineKeyboardMarkup()
    
    # Create individual buttons with custom labels and URLs
    btn_admin = InlineKeyboardButton(text="👨‍💼 Admin", url="https://t.me/GOAT_SERVlCE1")
    btn_shop = InlineKeyboardButton(text="🛍️ Online Shop", url="https://shoppy.gg/@GOATESHOPSERVICE")
    btn_channel = InlineKeyboardButton(text="📚 New Channel", url="https://t.me/GOATSERVICECHANEL")
    btn_group = InlineKeyboardButton(text="💬 Group Chat", url="https://t.me/GOATGROUPLINK")
    btn_support = InlineKeyboardButton(text="👨‍💻 Support", url="https://t.me/money_bitxh")
    
    # Add buttons to the keyboard (each add row creates new buttons on that line)
    markup.add(btn_admin)
    markup.add(btn_shop)
    markup.add(btn_channel, btn_group)
    markup.add(btn_support)

    # Reply with the welcome text and attach the buttons
    bot.reply_to(message, welcome_text, reply_markup=markup)

print("Bot with buttons is running...")
bot.infinity_polli
