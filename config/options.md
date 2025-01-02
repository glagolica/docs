# Options

Glagolica is not a tool that's leaned towards certain ecosystem,
therefore it does not provide programmatic way of setting certain configuration options via scripting languages.

We use TOML for our configuration, see [Config Lookup](./lookup.md) for more information regarding where to store config.

## `[site]`

### `default_lang`

Default language for your documentation is `en`,
but you're free to modify the value based on [ISO 639](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes):

```toml
[site]
default_lang = "en-US"
```

### `title`

Title value represents name of your documentation, not the Metadata.
Setting the value to some string would change some parts of your site and PDF,
including header and footer.

When serving web version of your documentation,
Glagolica will use this value in site's title based on `title_template`.

```toml
[site]
title = "This Documentation"
```

### `title_template`

To serve dynamic site metadata title, we use string template.

Following variables represent some values:

- `%name` - Name of the page AKA `title` value for frontmatter.
- `%title` - Title of the documentation, see above.

Default value is `%name | %title`.

```toml
[site]
title_template = "%name -.- %title"
```

// TODO
