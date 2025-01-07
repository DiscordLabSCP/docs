# DiscordLab.XPSystem

This modules links with the XPSystem plugin and requires v2.0.8 of the plugin to work. 
It adds a `getlevel` command which can get you the person's level and XP directly from the plugin and also has a logging feature to log when someone levels up.

??? info "Configuration"

    ```yaml
    DL.XPSystem:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel ID to send the level up messages to.
      channel_id: 0
      # The hex color code of the embed. Do not include the #.
      color: '3498DB'
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `channel_id` (ulong): The channel ID to send the level up messages to.
    - `color` (string): The hex color code of the embed. Do not include the #.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.