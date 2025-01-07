# DiscordLab.AdvancedLogging

Advanced logging is a module that allows you to log anything you want, as long as EXILED has it, this is NOT a module for beginners or people who have no clue about plugin development.

This is useful for logging events that DiscordLab doesn't already have modules for, but it is advanced hence it's name, but this should be a clear guide for you to follow. 
Once you've added the module and started your bot, you don't need to edit the config file, because there is a command you can use to add your own events, `/addlog`. 
Here when you run the command, a modal will show up with multiple different boxes, let me explain how each one works:

- **Handler** - This is the handler, so `Player` might be an example, this would get the Handler `Exiled.Events.Handlers.Player`.
- **Event** - This is the event, so `Died` might be an example, this would get the event `Died` from `Exiled.Events.Handlers.Player`, 
if you set your handler as `Player` that is. This would get the event `Exiled.Events.Handlers.Player.Died` and bind to it.
- **Message** - This is the message you want to send to the channel, here is the tricky part though, I do not write every single event that
is created using this method, so you need to add your own placeholder, they work like this, let's say we are bound to `Player.Died`,
here is what the message may look like for this case.
```
Player {Player.Nickname} has been killed.
```
So in this case you will see that `{Player.Nickname}` is a placeholder, you will need to go to the event args you are binding to
and find all the variables you need, you need to bind to that variable exactly or risk a null exception error. Capitals also matter.
Ignore the `ev.` part though, that is not required and is done for you.
- **Nullables** - This is a comma seperated list of nullable variables, and if one of the variables you mention inside here is null,
then the message will not be sent, this is useful for stuff like `Attacker` in the `Player.Died` event, as if the attacker is null,
then the message will not be sent.
- **Channel** - This is the channel ID you want to send the message to, you can get this by right-clicking a channel and clicking 
`Copy ID`. There is a tutorial on how to get IDs in the [Get started](/getting-started/installation) section.

After running this `/addlog` command, you shouldn't need to restart your server.

!!! warning
    
    Currently, player placeholders do not work on AdvancedLogging when there is a player involved, this is because of how AdvancedLogging is made and the effort to rebuild it in this way is just tedious.

??? info "Configuration"

    ```yaml
    DL.AdvancedLogging:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.