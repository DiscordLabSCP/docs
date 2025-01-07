# Installation

This guide will fully walk you through how to install DiscordLab and how to create a Discord bot to work with it.

## 0. Prerequisites

Before you start installing DiscordLab, you need to have a few things ready.

- EXILED 8.11.0 or higher
- A Discord account
- [Developer Mode for Discord](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID)

## 1. Installation

DiscordLab installation is quite simple, doesn't take that much effort and is pretty much like a normal plugin for EXILED.

DiscordLab requires EXILED 8.11.0, but it may work below that version, I have not tested because I can not test. 
If you do not have EXILED installed, this plugin will not work. 
First you should grab the latest `DiscordLab.Bot.dll` release from
[our GitHub](https://github.com/DiscordLabSCP/DiscordLab/releases/latest). 
After you have got the release, upload it to the Plugins folder in EXILED, and restart/start your server. 
After this, your configs will generate, so go to `EXILED/Configs/7777-config.yml` (1) and find DiscordLab under there. 
From there you need to add in your token and guild id.
{ .annotate }

1. This path will either be under `%appdata%` or `/.config/` depending on your setup, also if you have Exiled setup to go to a different folder, then change the path to that folder. You may also have seperated configs for each plugin or for 
each port you have, so make sure you are editing the right config file.

!!! danger
    
    If you do not have a token, your bot will not load.

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
DiscordLab:
  is_enabled: true
  debug: false
  # The token of the bot.
  token: token
  # The default guild where the bot will be used. You can set this individually for each module, but if a module doesn't have a guild id set, it will use this one.
  guild_id: 0
  # Enable auto updates if any modules are out of date.
  auto_update: true
```

You can leave the first 2 values as is, unless you are either debugging or disabling the bot. The `token` value is where you put the token you got from the [previous step](#21-token). The `guild_id` is where you put the guild ID
you got from the [previous step](#22-guild-id). The `auto_update` value is whether you want the bot to automatically update modules (and the main bot) when they are out of date. This only works with native DiscordLab modules and not external
ones made by the community.