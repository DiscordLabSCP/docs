# DiscordLab.BotStatus

This module makes it so the bot's status will change based on the status of the server, and is fully customisable. 
The status will show the current amount of players on the server, and you can edit it to go onto `Idle` mode when there is 0 people on the server. You can also edit the translations for 0 players too if needed,
incase 0/30 currently online does not fit what you want.

??? info "Configuration"

    ```yaml
    DL.BotStatus:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # Set the Discord bot's status to orange when the server is empty.
      idle_on_empty: false
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `idle_on_empty` (bool): Set the Discord bot's status to orange (idle) when the server is empty.