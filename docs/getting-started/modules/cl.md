# DiscordLab.ConnectionLogs

This module logs all connections and disconnections from the server to a specific channel, it does ignore all connections in the `Waiting for players` phase though to avoid spam and rate limits during that time, 
it can also cause hanging if sending too many messages at once, but we have a `Round started` message to counter-act this.

??? info "Configuration"

    ```yaml
    DL.ConnectionLogs:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel where the join logs will be sent.
      join_channel_id: 0
      # The channel where the leave logs will be sent.
      leave_channel_id: 0
      # The channel where the round start logs will be sent.
      round_start_channel_id: 0
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `join_channel_id` (ulong): The channel where the join logs will be sent.
    - `leave_channel_id` (ulong): The channel where the leave logs will be sent.
    - `round_start_channel_id` (ulong): The channel where the round start logs will be sent.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.