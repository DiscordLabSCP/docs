# DiscordLab.Bot

Here is all the API information relating to the main bot itself

## Handlers

Where you can find all the handlers

### DiscordBot

Where you can find all the Discord bot handling information

#### Property: Instance

Type: `Handlers.DiscordBot`

This is a static instance that can be used after the main DiscordLab.Bot plugin has been enabled. This contains all the values listed below

#### Property: Client

Type: `DiscordSocketClient`

This is the bot client itself and how you should interact with the Discord API if DiscordLab does not have a method for you

#### Method: Init()

Returns: `void`

Initialises the bot, do not run this in your own module.

#### Method: Unregister()

Returns: `void`

Disables the handler, do not run this in your own module.

#### Method: GetGuild(ulong id)

Params:

- `id` - The ID of the guild you want to get in `ulong`

Returns: `SocketGuild`

Get a guild by ID

## API.Extensions

Get all extension methods supplied by the main bot

### IMessageExtensions

Gets all extensions related to the `IMessage` class.

#### Method: IsUserMessage(this IMessage message)

Params:

- `message` - The `IMessage` you wish to check

Returns: `bool`

Checks if an `IMessage` is a user message and not a system message

## API.Features

Get all features the main bot has.

### DescriptionConstants

Get all constants for config variables.

#### Constant: GuildId

Type: `string`

Gets the string for GuildId in Config

#### Constant: IsEnabled

Type: `string`

Gets the string for IsEnabled in Config

#### Constant: Debug

Type: `string`

Gets the string for Debug in Config

### UpdateStatus

Public class for creating new modules that can be used inside DiscordLab to update/install modules/main bot.

#### Property: ModuleName

Type: `string`

Get or set the module name

#### Property: Version

Type: `Version`

Get or set the version

#### Property: Url

Type: `string`

Get or set the download URL of the module/main bot

## API.Interfaces

Get the interfaces used on classes

### IDLConfig

Get the DiscordLab config interface

#### Property: GuildId

Type: `ulong`

The Guild ID where this module/main bot should run

### IRegisterable

Get the interface for handlers so they can be found

#### Method: Init()

Returns: `void`

Here is where you should put your code for when the module/main bot is enabled

#### Method: Unregister()

Returns: `void`

Here is what you should put for when the module/main bot is disabled

### ISlashCommand

Here is the interface to create slash commands

#### Property: Data

Type: `SlashCommandBuilder`

The defining information about your slash command, like name, options, description, etc

#### Property: GuildId

Type: `ulong`

Where this command should be registered

#### Task: Run(SocketSlashCommand command)

Params:

- `command` - The `SocketSlashCommand`

This is what should happen when your slash command is executed

## Modules

Here is where all the modules are, includes methods which you should touch.

### HandlerLoader

A module that allows you to register all `IRegisterable` and `ISlashCommand` classes in your code.

Should be instantiated and bound to a variable so it can be run in `OnEnabled` and `OnDisabled`

#### Method: Load(Assembly assembly)

Params:

- `assembly` - Your project's `Assembly`

Returns: `void`

Load the module/main bot.

#### Method: Unload()

Returns: `void`

Unloads the module/main bot.

### QueueSystem

Run stuff in a queue based system

#### Method: QueueRun(string id, Action action)

Params:

- `id` - The unique ID of this queue, should be something that doesn't change unless it's part of a different queue.
- `action` - The code that should run when the initial 5 seconds is over

Returns: `void`

Run code after 5 seconds of it's initial call. Any requests to send the same ID again will be ignored.

### SlashCommandLoader

Allows you to manually load slash commands, recommended to use `HandlerLoader`.

Static class

#### Method: LoadCommands(Assembly assembly)

Params:

- `assembly` - Your plugin's Assembly

Returns: `void`

Loads the `ISlashCommand` classes in the plugin

#### Method: ClearCommands()

Returns: `void`

Clears all commands, dangerous.

### UpdateStatus

Auto-updater / update warning system. 

Static class

Also holds 2 classes `GitHubRelease` and `GitHubReleaseAsset`, allows interaction with the GitHub API Response

#### Property: Statuses

Type: `List<DiscordLab.Bot.API.Features.UpdateStatus>`

Get the currently created modules/main bot from the GitHub API

#### Method: WritePlugin(byte[] bytes, string name)

Params:

- `bytes` - The file content in a `byte[]` format.
- `name` - The plugin/module/main bot name

#### Task: DownloadPlugin(DiscordLab.Bot.API.Features.UpdateStatus status)

Params:
- `status` The `DiscordLab.Bot.API.Features.UpdateStatus` to download.

Downloads and writes a plugin to the plugins folder

#### Task: GetStatus()

Gets all DiscordLab modules/main bot via the GitHub API and adds them to the `Statuses` list.

### WriteableConfig

Allows you to read/write JSON config values from/to `EXILED/Configs/DiscordLab/config.json

#### Method: GetConfig

Returns: `JObject`

Get the current config

#### Method: WriteConfigOption(string key, JToken value)

Params:

- `key` - The key where the object should add the data, as type `string` 
- `value` - The data to save, as `JToken`

Returns: `void`

Write a config value