# Guide

!!! info

    You should really only reference `DiscordLab.Bot` in your project, unless you need to hook to another module for their Channel or whatever.

With `DiscordLab.Bot`, it has some methods that you can use to instantly start up your module. There is 2 interfaces which can be used, `IRegisterable` and `ISlashCommand`.

`IRegisterable` is used for registering Handlers, such as Discord bot related stuff and events, and `ISlashCommand` is used for registering Slash Commands.

If you use both interfaces on your classes, this allows for you to easily register your module with the bot. All you need to do is get `DiscordLab.Bot.API.Modules.HandlerLoader` and make a new instance of it, then in
`OnEnabled` call `HandlerLoader.Load()` and inside the Load method, pass in `Assembly`. This will then load all the handlers and slash commands within your module. Also don't forget to remove the handlers in the `OnDisabled`
method, you can do this by calling `HandlerLoader.Unload()`, no need for `Assembly` in this one though.

In `DiscordLab.Bot.Handlers` there is a `DiscordBot` class which you can use to interact with the bot which is logged in.
This class has an `Instance` property which means you can just do `DiscordLab.Bot.Handlers.DiscordBot.Instance` to get the bot instance. This has
a `Client` property which is the main Discord client and a `Guild` property which is the guild the main bot has referenced in the config.

You should always bind stuff to the `Guild` property for sending messages or finding channels, but you may need to
use the `Client` property sometimes too, like for the `Ready` event. When doing the Ready event, you can just add the
event on like a normal event, so usually it would be like this:

```csharp
DiscordLab.Bot.Handlers.DiscordBot.Instance.Client.Ready += OnReady;
```

```csharp
private async Task OnReady()
{
    // Do stuff here
}
```

If you want to access Guild in the ready event, I would recommend doing a `Timing.CallDelayed` as Guild is fetched in the Ready
event too, so it may not be available straight away.

Also, you can just do any event that Discord.Net supports, not just Ready.

Last thing, make sure channels are always text channels if you plan on sending/receiving messages, `Guild.GetTextChannel` is a good method to use.