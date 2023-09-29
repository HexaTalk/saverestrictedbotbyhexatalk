# saverestrictedbotbyhexatalk
#Github.com/Vasusen-code

from pyrogram import Client

from telethon.sessions import StringSession
from telethon.sync import TelegramClient

from decouple import config
import logging, time, sys

logging.basicConfig(format='[%(levelname) 5s/%(asctime)s] %(name)s: %(message)s',
                    level=logging.WARNING)

# variables
API_ID = config("29509604", default=None, cast=int)
API_HASH = config("7543d780627ea4a25da5fe5696167440", default=None)
BOT_TOKEN = config("6015865589:AAHjjlOY0wyyaMjFk6lENChQpYivdBbA2TY", default=None)
SESSION = config("BQHCR-QAJ6T_mUXBMY3pkHJ9PlH3ofKJiJHrZgw_exEp7auLF4vGo-xYLgetEEAbTnktF8MoJ0bllOW-TGIh_lTKOe7hLIXhhijjpomrfHNLJqepphziuFe3jKc0XiDOMWKEhMu0GbiSJ8iDTKX6fIJ5-3-25N16wmmMxZQCgnrOUvJm0g-2UJ2v7n3hAyWcJ6K7lBv2Eq-nehI7hQPi3MwYBOaQR9mFY2UhVwbAenfwPyPDf-CvpUtUqiJdLWjGVEv-6mz30HoVIGSgZwDaCe2Pohdt5I4ZMJIj5JLuUE8Hx7zrUXhMyH8k7XbUwTFZJlS3a-5-kLyFT4mc5LKMgfL_ZMf0kAAAAAFj7IC5AA", default=None)
FORCESUB = config("faaltuhaiye", default=None)
AUTH = config("5971411129", default=None, cast=int)

bot = TelegramClient('bot', API_ID, API_HASH).start(bot_token=BOT_TOKEN) 

userbot = Client("saverestricted", session_string=SESSION, api_hash=API_HASH, api_id=API_ID) 

try:
    userbot.start()
except BaseException:
    print("Userbot Error ! Have you added SESSION while deploying??")
    sys.exit(1)

Bot = Client(
    "SaveRestricted",
    bot_token=BOT_TOKEN,
    api_id=int(API_ID),
    api_hash=API_HASH
)    

try:
    Bot.start()
except Exception as e:
    print(e)
    sys.exit(1)
