# DiscordLab.ModerationLogs

This module allows you to log all moderation/administrative actions on your SCP server, `DiscordLab.Moderation` links directly to this as well for moderation logs, but isn't required for it to work.

??? info "Configuration"

    ```yaml
    DL.ModerationLogs:
    # Whether the module is enabled or not.
      is_enabled: true
      # Whether the module is in debug mode or not.
      debug: false
      # The channel where the ban logs will be sent.
      ban_channel_id: 0
      # The hex color code of the ban embed. Do not add the #.
      ban_color: '3498DB'
      # The channel where the unban logs will be sent.
      unban_channel_id: 0
      # The hex color code of the unban embed. Do not add the #.
      unban_color: '3498DB'
      # The channel where the kick logs will be sent.
      kick_channel_id: 0
      # The hex color code of the kick embed. Do not add the #.
      kick_color: '3498DB'
      # The channel where the mute logs will be sent.
      mute_channel_id: 0
      # The hex color code of the mute embed. Do not add the #.
      mute_color: '3498DB'
      # The channel where the unmute logs will be sent.
      unmute_channel_id: 0
      # The hex color code of the unmute embed. Do not add the #.
      unmute_color: '3498DB'
      # The channel where the warn logs will be sent.
      admin_chat_channel_id: 0
      # The hex color code of the admin chat embed. Do not add the #.
      admin_chat_color: '3498DB'
      # The channel where reports will be sent.
      report_channel_id: 0
      # The hex color code of the report embed. Do not add the #.
      report_color: '3498DB'
      # The channel where remote admin logs will be sent.
      remote_admin_channel_id: 0
      # The hex color code of the remote admin embed. Do not add the #.
      remote_admin_color: '3498DB'
      # The channel where error logs will be sent.
      error_log_channel_id: 0
      # The hex color code of the error logging embed. Do not add the #.
      error_log_color: '3498DB'
      # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
      guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `ban_channel_id` (ulong): The channel where the ban logs will be sent.
    - `ban_color` (string): The hex color code of the ban embed. Do not add the #.
    - `unban_channel_id` (ulong): The channel where the unban logs will be sent.
    - `unban_color` (string): The hex color code of the unban embed. Do not add the #.
    - `kick_channel_id` (ulong): The channel where the kick logs will be sent.
    - `kick_color` (string): The hex color code of the kick embed. Do not add the #.
    - `mute_channel_id` (ulong): The channel where the mute logs will be sent.
    - `mute_color` (string): The hex color code of the mute embed. Do not add the #.
    - `unmute_channel_id` (ulong): The channel where the unmute logs will be sent.
    - `unmute_color` (string): The hex color code of the unmute embed. Do not add the #.
    - `admin_chat_channel_id` (ulong): The channel where the admin chat logs will be sent.
    - `admin_chat_color` (string): The hex color code of the admin chat embed. Do not add the #.
    - `report_channel_id` (ulong): The channel where reports will be sent.
    - `report_color` (string): The hex color code of the report embed. Do not add the #.
    - `remote_admin_channel_id` (ulong): The channel where remote admin logs will be sent.
    - `remote_admin_color` (string): The hex color code of the remote admin embed. Do not add the #.
    - `error_log_channel_id` (ulong): The channel where error logs will be sent.
    - `error_log_color` (string): The hex color code of the error logging embed. Do not add the #.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.