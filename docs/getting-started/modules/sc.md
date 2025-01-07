# DiscordLab.StatusChannel

Sends and updates an embed inside a specific channel which shows who is online and how many are online, fully customisable.

??? info "Configuration"

    ```yaml
    DL.StatusChannel:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel where the status message will be sent / edited.
      channel_id: 0
      # The hex color code of the embed. Do not add the #.
      color: '3498DB'
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `channel_id` (ulong): The channel where the status message will be sent / edited.
    - `color` (string): The hex color code of the embed. Do not add the #.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.