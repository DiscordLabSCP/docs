# DiscordLab.AdminLogs

This module logs all things which happen on the local admin space. Currently only server start and error logging, but more to come in future.

??? info "Configuration"

    ```yaml
    DL.AdminLogs:
        # Whether the module is enabled or not.
        is_enabled: true
        # Whether the module is in debug mode or not.
        debug: false
        # The channel where error logs will be sent.
        error_log_channel_id: 0
        # The hex color code of the error logging embed. Do not add the #.
        error_log_color: '3498DB'
        # The channel where server start logs will be sent.
        server_start_channel_id: 0
        # The hex color code of the server start embed. Do not add the #.
        server_start_color: '3498DB'
        # The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.
        guild_id: 0
    ```

    - `is_enabled` (bool): Whether the module is enabled or not.
    - `debug` (bool): Whether the module is in debug mode or not.
    - `error_log_channel_id` (ulong): The channel where error logs will be sent.
    - `error_log_color` (string): The hex color code of the error logging embed. Do not add the #.
    - `server_start_channel_id` (ulong): The channel where server start logs will be sent.
    - `server_start_color` (string): The hex color code of the server start embed. Do not add the #.
    - `guild_id` (ulong): The guild ID where this module will be used. If not set (value = 0), it will use the default guild ID.