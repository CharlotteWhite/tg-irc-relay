# Telegram-IRC Relay Bot

A lightweight Telegram-IRC relay bot written in Python. It won't eat messages or memory.

Run: `python3 relay.py [-d]`

`-d` for debug mode.

## Config

The config file must be `config.json`, see the example.
You must disable the privacy mode for your bot.

* __botid__: The number in the token before `:`
* __botname__: Your bot's name
* __groupid__: The Telegram group id to be forwarded. To get it, enable debug mode `-d`, add your bot into the group, say something in the group, and copy the 'message'/'chat'/'id' from the "Msg arrived" line (without `-`). This ID MUST be positive.
* __groupname__: The group's name
* __i2t__: true/false, Enable/disable IRC to Telegram forwarding
* __ircignore__: Ignore users that match the regex. Don't be empty, use "^$" to disable.
* __ircbotid__: The ID of the bot which forwards messages. Usually it should be the same as `botid`, except that there is another bot responsible for this.
* __ircbotname__: The name (in Telegram) of the forwarding bot. Usually it should be the same as `botname`
* __ircchannel__: The IRC channel to forward
* __ircnick__: The bot's nickname in IRC
* __ircport__, __ircserver__, __ircssl__, __ircpass__: How to connect to the IRC server. `ircpass` is optional, can be blank.
* __offset__: Use 0 for the first time, don't manually change it after
* __shownick__: true/false, Enable/disable prefixing of messages sent to Telegram with the IRC nick of the sender (enabled by default)
* __colorize__: true/false, Enable/disable coloring item in IRC (disabled by default)
* __usercolor__, __mentioncolor__, __replytextcolor__: "[usercolor] Re mentioncolor 「replytextcolor」: Text" (00-15 or 99)
* __t2i__: true/false, Enable/disable Telegram to IRC forwarding
* __token__: Your bot's token
* __servemedia__ (_Optional_): Can be "" or "self" or "vim-cn" or "linx".
* __cachepath__ (When "servemedia" is not empty): Where should the images be stored. **YOU are responsible for clearing this directory.** (eg. set up a cron job of `find $CACHEPATH -type f -mtime +1 -delete`.)
* __serveurl__ (When "servemedia" is "*self*"): The url prefix where the images can be retreived from your server, which should be an alias of __cachepath__.
* __linx_api_url__ (When "servemedia" is "*linx*"): API address of self-hosted [linx](https://github.com/andreimarcu/linx-server) instance.
* __linx_size_limit__ (When "servemedia" is "*linx*"): Maximum size of file to be forwarded. In bytes. 10MB by default.
* __tg_admin_list__: A string of mentions used to notify administrators with /admin.
* __paeeye__: If set to true, don't forward messages starting with '//' or '@@@'.

## See also

* [orz-telegram-bot](https://github.com/wfjsw/orz-telegram-bot), a node.js version.
* [tg-chatdig](https://github.com/gumblex/tg-chatdig), on which this bot is based.
