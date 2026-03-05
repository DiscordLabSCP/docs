# DiscordLab.ConnectionLogs

This module logs all connections and disconnections from the server to a specific channel, it does ignore all connections in the `Waiting for players` phase though to avoid spam and rate limits during that time, 
it can also cause hanging if sending too many messages at once, but we have a `Round started` message to counter-act this.