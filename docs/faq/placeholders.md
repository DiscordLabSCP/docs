# Placeholders

## What are placeholders?

Placeholders are special strings that are replaced with actual values when the message is sent. They are used to personalize messages and make them fit your needs.

Placeholders include providing information about the player, the server, the map and more.

## How do I use placeholders?

Each plugin has a placeholder system in place and also the global placeholder system, you can find some of the placeholders available in the module's translation files. These placeholders are usually only module specific and are not available
in other modules.

Placeholders go inside the translation like this `{placeholder}`. Just replace the `placeholder` with the actual placeholder you want to use.

Placeholders are only replaced in some parts of a translation. This can be changed by modifying the `translated_fields: field1, field2, ...`.
By default, placeholders are replaced in the following parts of a message: Message, EmbedDescription, EmbedFieldValues, EmbedFooterText.
Full list of options: `None, Message, EmbedTitle, EmbedDescription, EmbedThumbnailUrl, EmbedImageUrl, EmbedUrl, EmbedFieldNames, EmbedFieldValues, EmbedAuthorName, EmbedAuthorUrl, EmbedAuthorIconUrl, EmbedFooterText, EmbedFooterIconUrl`

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
- `{elapsedtimerelative}` - Shows the relative time since the round started
- `{secondssince}` - Shows the seconds since the round started
- `{minutessince}` - Shows the minutes since the round started

### Map based placeholders

- `{seed}` - Gets the current map seed
- `{decontstate}` - Gets the current decontamination state
- `{isdecont}` - Is LCZ currently decontaminated
- `{isdecontenabled}` - Is decontamination enabled
- `{remainingdeconttime}` - Gets how long until decontamination begins

### Round based placeholders

- `{killcount}` - Gets the current kill count for this round
- `{elapsedtime}` - Gets the current elapsed time
- `{escapedscientistscount}` - Gets the escaped scientists count
- `{inprogress}` - Check if the round is in progress
- `{isended}` - Check if the round is ended
- `{isstarted}` - Check if the round has started
- `{islocked}` - Check if the round is locked
- `{changedintozombiescount}` - The amount of zombies (unsure if currently or overall)
- `{escapeddclassescount}` - The amount of Class-D's who have escaped
- `{islobbylocked}` - Check if the lobby is locked
- `{scpkillcount}` - Check how many people the SCPs have killed
- `{alivescpcount}` - Check how many SCPs are alive
- `{roundcount}` - Check how many rounds there has been since server start

### Server based placeholders

- `{maxplayers}` - Check the max player count on the server
- `{name}` - Gets the server name
- `{nameparsed}` - Gets the server name, but with no styling and no trackers
- `{port}` - Gets the server port
- `{ip}` - Gets the server IP
- `{playercount}` - Gets the current players on the server (may include NPCs)
- `{playercountnonpcs}` - Gets the current player count, with no NPCs
- `{tps}` - Gets the server's TPS
- `{version}` - Gets the server version
- `{isbeta}` - Gets whether the server is a beta server
- `{isfriendlyfire}` - Is friendly fire enabled?

## Player placeholders

!!! question "How do I know if a player placeholder is available?"
    
    If the translation you are editing has references to a player in it, the below placeholders are available to use.

!!! info "Figuring out prefixes"

    Prefixes are required for player placeholders to work, this is due to some events having multiple players involved. In most cases it is just `player`, but in some cases there may be `attacker` or `issuer` as well.
    Make sure you select the right prefix for the right player.

??? question "What is a prefix?"

    A prefix is a word that comes before the placeholder, it is used to determine which player the placeholder is referring to. For example, if you have a translation that says `player has died`, you would use the `player` prefix.

The below placeholders do not contain the `{}` or the prefix, you will need to add these yourself.

- `name` - Gets the player's nickname
- `nickname` - Gets the player's nickname
- `userid` - Gets the player's ID (e.g. 2, 6, 24)
- `role` - Gets the player's role name (e.g. Scientist, Nine-Tailed Fox Private)
- `roletype` - Gets the player's role type ID
- `team` - Gets the player's team (e.g. NTF, Chaos)
- `faction` - Gets the player's faction
- `health` - Gets the player's health
- `maxhealth` - Gets the player's max health
- `group` - Gets the player's group name
- `badgecolor` - Gets the player's badge color
- `hasdnt` - Does the player have Do Not Track enabled
- `hasra` - Does the player have remote admin access
- `room` - What room the player is in
- `zone` - What zone the player is in
- `position` - Where is the player located
- `ping` - Player's current ping
- `permissiongroup` - What permission does this player have

### Private placeholders (Should not be sent to public channels)

- `id` - Gets the player's user ID (e.g. ...@steam or ...@northwood)
- `ip` - Gets the player's IP (if you use this, make sure it's in a private channel or you could lose verified status on your server, we are not liable for this happening)
- `isglobalmod` - Is the player a global moderator
- `isnorthwood` - Is the player Northwood staff (shouldn't be shown just in case the user has DNT enabled, which most NW staff do)

??? question "Why are some of these `Unknown`?"

    Some of these placeholders may return `Unknown` if the player doesn't have the information you are requesting, i.e. if you are requesting badge but the player doesn't have a badge, it will return `Unknown`.