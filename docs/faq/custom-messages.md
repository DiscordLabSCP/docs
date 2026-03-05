# Custom Messages

With DiscordLab, it is super easy to create your own custom messages via the `translation.yml` configs for modules. These allow you to put in [placeholders](/faq/placeholders) but more than just that.

For instance, in a translation you can either set up just a simple plain message which sends to Discord, looking like the ones you all know, or you can do an `embed` which is the special kind of formatting that bots are allowed to do.

!!! info

    It is possible to do both a raw message and an embed!

Here is a setup of a normal message

```yaml
example:
  message: Hi I am a message which will get sent during a random event or command response.
```

You can expand on this to add an embed, to add an embed you do this:

```yaml
example:
  message: Hi I am a message which will get sent during a random event or command response.
  embed:
    title: Hi I am an embed
    description: I also have a description field
```

Tada! A crisp embed! Now this will have little to no formatting, but we can expand on it below as such:

```yaml
example:
  message: Hi I am a message which will get sent during a random event or command response.
  embed:
    # The title of the embed
    title: Embed title
    # The text that will appear as a description in the embed
    description: Embed description
    # Fields here are like little boxes for an embed, can add more information here, allows stuff to be seperated better!
    fields:
    - name: Field name
      # Think of this like a field description
      value: Field description
      # This field here means that will it show side by side of other inline fields
      is_inline: true
    # Embed colour! Can be hex with a # or 0x, doesn't matter.
    color: '#000000'
    # Thumbnail image URL, this appears in the top right of the embed
    thumbnail_url: https://example.com
    # This is the big image URL
    image_url: https://example.com
    # This makes it so the title is clickable and will lead you to the URL given.
    url: https://example.com
    # A footer is something that appears at the bottom of something, in this case, the bottom of the embed.
    footer:
      # The text to appear in the footer.
      text: DiscordLab is awesome!
      # You can add an icon URL! (optional)
      icon_url: https://example.com
    # Author is placed at the top of the embed, can be used for a server name for example.
    author:
      # If going for the server name route, put your servers name here!
      name: My awesome server!
      # The image to appear as an icon (optional)
      icon_url: https://example.com
      # Where should clicking the author lead to? (optional)
      url: https://example.com
    # Whether a timestamp will be generated in the footer of the embed using the user's local time (optional)
    timestamp: true
```

!!! info

    Only one of the following has to be present in an embed for it to work: `title`, `description`, `thumbnail_url`, `image_url`, `author.name`, or one `field` (under `fields`). As long as you have one of these fields, you can mix and match your embeds to your need!

??? danger "My server is throwing errors whilst editing my configs!"

    Please put your configs into a `YAML Linter`, these tools will typically help you figure out issues and sort them yourselves. One I recommend is https://www.yamllint.com/, just turn off the `Reformat` option.

And that is a complete embed! You can also remove the `message` component from the config if you wish.

    