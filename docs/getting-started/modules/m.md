# DiscordLab.Moderation

This module allows you to do moderation/administrative actions on your SCP server without needing to go onto the server, it makes 3 commands which allow you to interact with the server, the command names can be configured.

??? info "Configuration"

    ```yaml
    DL.Moderation:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID. For this module, this just affects where the commands can be used.