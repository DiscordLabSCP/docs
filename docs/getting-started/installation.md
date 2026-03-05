# Installation

This guide will fully walk you through how to install DiscordLab and how to create a Discord bot to work with it.

!!! warning

    DiscordLab v2 isn't an EXILED plugin anymore, it utilises LabAPI to ensure that DiscordLab is ready and stable on every new version of SCP:SL.

## 0. Prerequisites

Before you start installing DiscordLab, you need to have a few things ready.

- A Discord account
- [Developer Mode for Discord](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID)

## 1. Installation

DiscordLab installation is quite simple, doesn't take that much effort and is pretty much like a normal plugin for LabAPI.

First you should grab the latest `DiscordLab.Bot.dll` and `dependencies.zip` from
[our GitHub releases](https://github.com/DiscordLabSCP/DiscordLab/releases/latest). 
After you have got the files, upload `DiscordLab.Bot.dll` to the `plugins/global` folder in LabAPI, then extract `dependencies.zip` into `dependencies/global` inside of LabAPI too.
After this, your configs will generate, so go to `SCP Secret Laboratory/LabApi/configs/port(1)/DiscordLab` (2) and find DiscordLab under there. 
From there you need to add in your token and guild id.
{ .annotate }

1. Replace this with the port of your server, default is 7777 but not every server has that port. If you are unsure what a port is, it is the thing after the `:` in your IP address.
2. If running on Windows, this path will be under `%appdata%` which can be directly inputted into your Windows search bar. If you are on a control panel with a file explorer in-built, it will typically be in the `.config` folder. If you are on your own Linux distribution, this will be under `~/.config`.

!!! danger
    
    If you do not have a token, your bot will not load.

??? question "My server is based in a country which has blocked Discord, how do I set this up to work?"

    You should follow the above steps, but you also need to setup a proxy server which you can then put the URL into the config for, under `proxy_url`.

## 2. Setup
### 2.1. Token

??? info "What is a token?"

    A token in this sense is something that allows you to connect to a Discord account (including bot/app accounts) without a username, password and 2FA. This sounds dangerous to give out right? Because it is, 
    you should never give out your Discord bot token or your user account token, and yes, user account tokens exist and if you use Discord, that's how you are logged in, 
    your username and password changes into a token that is then used to connect to Discord.

For DiscordLab to work, you need to get a token for a Discord bot made for your server. If you don't already have a bot made, go to [discord.dev](https://discord.com/developers/applications) where you can create your bot. 
If requested to log-in, please do so. From here click `New application` in the top right, and give it a name and agree to the ToS, only if you do accept the ToS. After you are inside your new bot's web page, 
head to the `Bot` page on the left hand side and click `Reset Token`. You will then be asked to provide authentication if you have 2FA enabled, just complete it and grab the token. 
After you have it I would recommend saving this in a secure place like a password manager with a secure note feature. Recommended: Scroll down the page and find the `Public bot` option, 
disable this to avoid people adding your bot to their servers.

After you have the token, save this somewhere until we get to the [configuration](#3-configuration) section.

### 2.2. Guild ID

??? info "What is a guild?"

    A guild is a fancy word Discord uses for a server, so when you see `guild` in the config, it means server.

Now to get the guild IDs, first you should figure out what your main server is (if you have 2 or more). Once you have found your server, 
see if you already have developer mode on by right-clicking the server and seeing if you have a `Copy Server ID` option then click that and put that in the guild id section. 
If you do not have that option, Read [this guide](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID) on how to get the option, then just repeat what I said.

You should also save this for the [configuration](#3-configuration) section.

### 2.3. Inviting the bot to your server

From here you will need to invite the bot to your server(s). 
Head over to the `OAuth2` page and scroll down until `OAuth2 URL Generator` and select `bot` and `applications.commands` and scroll down further to give your bot any permissions you want, 
I recommend `Administrator` but it doesn't need that to work. After that, continue scrolling until you get to the bottom and make sure `Integration type` is `Guild Install`. 
Now copy that generated URL and paste it into your browser, then add the bot to the servers you want.

## 3. Configuration

The default configuration for DiscordLab looks like this:

```yaml
# The token of the bot.
token: token
# The default guild ID. Each module that has their guild ID set to 0 has their guild ID set to this.
guild_id: 0
# Whether the plugin should check for DiscordLab updates.
auto_update: true
# The proxy URL to use. Should only be used in very specific cases like Discord being banned in your country. Please set to empty to not use.
proxy_url: ''
# Enable debugging mode, useful to enable when needing to debug for developers.
debug: false
```

### Definitions:

- `token` - This is the value you got from the [Token](#21-token) step.
- `guild_id` - This is the ID of the server you wish to make the default for the bot. To gain this you can go to the [Guild ID](#22-guild-id) step.
- `auto_update` - Whether to update the bot + modules whenever they receive an update. These only work for native modules, not ones made by other community members.
- `proxy_url` - Only fill this in when your server's location is blocked from using Discord, you should put a proxy URL in here. Otherwise, please do not fill this out.
- `debug` - You should enable this whenever asked by the support team, or you want to debug what an issue is yourself.
