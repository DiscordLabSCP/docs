# DiscordLab.RoundLogs

This module will log most things related to the current round, like round start/finish, player cuffed/uncuffed and Chaos/NTF spawn.

??? info "Configuration"

    ```yaml
    DL.RoundLogs:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel ID to send the round start messages to.
      round_start_channel_id: 0
      # The channel ID to send the round end messages to.
      round_end_channel_id: 0
      # The channel ID to send the cuff logs to. (When a player gets cuffed)
      cuffed_channel_id: 0
      # The channel ID to send the uncuff logs to. (When a player gets uncuffed)
      uncuffed_channel_id: 0
      # The channel ID to send the Chaos spawn logs to.
      chaos_spawn_channel_id: 0
      # The channel ID to send the NTF spawn logs to.
      ntf_spawn_channel_id: 0
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `round_start_channel_id` (ulong): The channel ID to send the round start messages to.
    - `round_end_channel_id` (ulong): The channel ID to send the round end messages to.
    - `cuffed_channel_id` (ulong): The channel ID to send the cuff logs to. (When a player gets cuffed)
    - `uncuffed_channel_id` (ulong): The channel ID to send the uncuff logs to. (When a player gets uncuffed)
    - `chaos_spawn_channel_id` (ulong): The channel ID to send the Chaos spawn logs to.
    - `ntf_spawn_channel_id` (ulong): The channel ID to send the NTF spawn logs to.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.