# DiscordLab.DeathLogs

This module logs all deaths (with also all death types) from the server to a specific channel. This allows you to log every type of death you want.

??? info "Configuration"

    ```yaml
    DL.DeathLogs:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel where the normal death logs will be sent.
      channel_id: 0
      # The channel where the death logs of cuffed players will be sent. Keep as default value to disable. Disabling this will make it so logs are only sent to the normal death logs channel, but without the cuffed identifier.
      cuffed_channel_id: 0
      # The channel where logs will be sent when a player dies by their own actions, or just they died because of something else.
      self_channel_id: 0
      # The channel where logs will be sent when a player dies by a teamkill.
      team_kill_channel_id: 0
      # If this is true, then the plugin will ignore the cuff state of the player and send the death logs to the normal death logs channel.
      scp_ignore_cuffed: true
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `channel_id` (ulong): The channel where the normal death logs will be sent.
    - `cuffed_channel_id` (ulong): The channel where the death logs of cuffed players will be sent. Keep as default value to disable. Disabling this will make it so logs are only sent to the normal death logs channel, but without the cuffed identifier.
    - `self_channel_id` (ulong): The channel where logs will be sent when a player dies by their own actions, or just they died because of something else.
    - `team_kill_channel_id` (ulong): The channel where logs will be sent when a player dies by a team-kill.
    - `scp_ignore_cuffed` (bool): If this is true, then the plugin will ignore the cuff state of the player and send the death logs to the normal death logs channel.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.