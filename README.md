# slack-to-telegram-bot
Small hack for integration Asana.com and Telegram.me using slack service as a transport service. Based on https://github.com/trestoa/slack-to-telegram-bot repo.
!! Be aware of hard-coded filter of Slack BOT ID, remove it or replace with a proper one before using it on your slack channel !!

Bot for forwarding slack messages to telegram.

## Usage
Tested on Python 3.5.

For configuration, set the following environment variables:
```
$ export SLACK_TOKEN=''     # Slack bot token
$ export TELEGRAM_TOKEN=''  # Telegram bot token
$ export TELEGRAM_TARGET='' # Target chat
```
For the target chat, see http://stackoverflow.com/questions/32423837/telegram-bot-how-to-get-a-group-chat-id-ruby-gem-telegram-bot.

Run with:
```
python bot.py # <- You could not have guessed that!
```
You can also build and use the docker image:
```
docker build -t <docker-image-url:docker-image-tag> .
docker push <docker-image-url:docker-image-tag>
docker run -d --name slack-to-telegram-bot --restart=always -e TELEGRAM_TOKEN='$TELEGRAM_TOKEN' -e TELEGRAM_TARGET='$TELEGRAM_TARGET' -e SLACK_TOKEN='$SLACK_TOKEN' <docker-image-url:docker-image-tag>
```

## Depencencies
- [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot)
- [slackclient](https://github.com/slackapi/python-slackclient)

Install the dependencies via pip: `pip install -r requirements.txt`.

## License
Licensed under the [Unlicense](http://unlicense.org/).
Do with it whatever you want.
