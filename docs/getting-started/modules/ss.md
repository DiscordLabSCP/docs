# DiscordLab.SCPSwap

This module connects with any SCP Swap plugin and will log any swaps between 2 SCPs. This only works on EXILED 9 unfortunately.

??? info "Configuration"

    ```yaml
    DL.SCPSwap:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel where the swap logs will be sent.
      channel_id: 0
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `channel_id` (ulong): The channel where the swap logs will be sent.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.