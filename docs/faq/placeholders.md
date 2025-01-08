# Placeholders

## How do I determine if a translation supports placeholders?

Translations that support placeholders will have placeholders already in them. If you see a translation with a placeholder like `{placeholder}` in it, then that translation supports placeholders.

## What are placeholders?

Placeholders are special strings that are replaced with actual values when the message is sent. They are used to personalize messages and make them fit your needs.

Placeholders include providing information about the player, the server, the map and more.

## How do I use placeholders?

Each plugin has a placeholder system in place and also the global placeholder system, you can find some of the placeholders available in the module's translation files. These placeholders are usually only module specific and are not available
in other modules.

Placeholders go inside the translation like this `{placeholder}`. Just replace the `placeholder` with the actual placeholder you want to use.

There is global placeholders and player placeholders. Global placeholders are available in all modules and player placeholders are available wherever a player is involved. More information in the sections below.

## Global placeholders

These are placeholders that are available in all modules and all translations that support placeholders

### Time based placeholders

- `{time}` - Shows the current time in Discord's native time box
- `{timet}` - Does the same as above, but using the t suffix
- `{timetlong}` - Does the same thing as time, but using the T suffix
- `{timed}` - Does the same thing as time, but using the d suffix
- `{timedlong}` - Does the same thing as time, but with the D suffix
- `{timef}` - Does the same thing as time, but with the f suffix
- `{timeflong}` - Does the same thing as time, but with the F suffix
- `{timer}` - Shows the relative time since the thing happened, in Discord's native time box

### Map based placeholders

- `{seed}` - Gets the current map seed
- `{decontstate}` - Gets the current decontamination state
- `{isdecont}` - Is LCZ currently decontaminated
- `{isdecontenabled}` - Is decontamination enabled

### Round based placeholders

- `{killcount}` - Gets the current kill count for this round
- `{alivesides}` - Gets a list of currently alive sides
- `{alivesidescount}` - Get the count of alive sides
- `{elapsedtime}` - Gets the current elapsed time
- `{elapsedtimerelative}` - Gets the currently elapsed time, but in a relative form using Discord's native time box
- `{roundstart}` - Gets the time the round started, using Discord's native time box
- `{escapedscientistscount}` - Gets the escaped scientists count
- `{inprogress}` - Check if the round is in progress
- `{isended}` - Check if the round is ended
- `{isstarted}` - Check if the round has started
- `{islocked}` - Check if the round is locked
- `{islobby}` - Check if everyone is in the lobby
- `{changedintozombiescount}` - The amount of zombies (unsure if currently or overall)
- `{escapeddclassescount}` - The amount of Class-D's who have escaped
- `{islobbylocked}` - Check if the lobby is locked
- `{scpkillcount}` - Check how many people the SCPs have killed
- `{alivescpcount}` - Check how many SCPs are alive

### Server based placeholders

- `{maxplayers}` - Check the max player count on the server
- `{name}` - Gets the server name
- `{nameparsed}` - Gets the server name, but with no styling and no trackers
- `{port}` - Gets the server port
- `{ip}` - Gets the server IP
- `{playercount}` - Gets the current players on the server (may include NPCs)
- `{playercountnonpcs}` - Gets the current player count, with no NPCs
- `{tps}` - Gets the server's TPS

## Player placeholders

!!! question "How do I know if a player placeholder is available?"
    
    If the translation you are editing has references to a player in it, the below placeholders are available to use.

!!! info "Figuring out prefixes"

    Prefixes are required for player placeholders to work, this is due to some events having multiple players involved. In most cases it is just `player`, but in some cases there may be `attacker` or `issuer` as well.
    Make sure you select the right prefix for the right player.

??? question "What is a prefix?"

    A prefix is a word that comes before the placeholder, it is used to determine which player the placeholder is referring to. For example, if you have a translation that says `player has died`, you would use the `player` prefix.

The below placeholders do not contain the `{}` or the prefix, you will need to add these yourself.

- `nickname` - Gets the player's nickname
- `id` - Gets the player's user ID (e.g. ...@steam or ...@northwood)
- `ip` - Gets the player's IP (if you use this, make sure it's in a private channel or you could lose verified status on your server, we are not liable for this happening)
- `userid` - Gets the player's ID (e.g. 2, 6, 24)
- `role` - Gets the player's role name (e.g. Scientist, Nine-Tailed Fox Private)
- `roletype` - Gets the player's role type ID
- `team` - Gets the player's team (e.g. NTF, Chaos)
- `side` - Gets the player's side
- `health` - Gets the player's health
- `maxhealth` - Gets the player's max health
- `group` - Gets the player's group name
- `badge` - Gets the player's badge
- `badgecolor` - Gets the player's badge color

??? question "Why are some of these `Unknown`?"

    Some of these placeholders may return `Unknown` if the player doesn't have the information you are requesting, i.e. if you are requesting badge but the player doesn't have a badge, it will return `Unknown`.