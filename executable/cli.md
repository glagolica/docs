# CLI

Executable represents a CLI with multiple different commands.

## `glag`

Simply running `glag` CLI would start an http server with default port as 2222 i.e. http://localhost:2222.

```sh
$ glag
```

### `--version` / `-v`

This returns version to stdout with `v` prefix i.e. `v0.0.0`.

```sh
$ glag --version
$ glag -v
```

### `--help` / `-h`

To return help information regarding usage of glagolica, we provide an according flag.

```sh
$ glag --help
$ glag -h
```

### `--port` / `-p`

To customize port, use `--port` flag with given number:

```sh
$ glag --port 3000
$ glag -p 3000
```

### `--prod`

By default, Glagolica would be using development mode when serving web version of your documentation.
This enables the use of Hot Module Replacement.
You would want to remove this feature to decrease JS bundle size served in production.

```sh
$ glag --prod
$ glag --port 80 --prod
```

## `glag pdf`

Running this command will generate single pdf file with all the given documentation,
including manuals and reference.

```sh
$ glag pdf
```

### `--noir`

By providing noir flag, Glagolica will generate black-and-white documentation file especially useful for printing purposes.

```sh
$ glag pdf --noir
```

## `glag web`

Running this command will generate HTML/CSS/JS export bundle,
similar to simple served documentation via `glag`.

```sh
$ glag web
```

## `glag init`

Running this command will guide you through some additional steps for configuring [your configuration file for Glagolica](../config/options.md).

```sh
$ glag init
```
