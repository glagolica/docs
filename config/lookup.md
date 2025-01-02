# Config Lookup

By default, Glagolica looks up for its config file `glagolica.toml` in the directory where CLI is used,
then it checks `.config/glagolica.toml` of current working directory.

> [!NOTE]
> Glagolica looks up for config file in `.config` because it follows [this proposal](https://github.com/pi0/config-dir).

If Glagolica does not find the config file, it will go up until it stops upon finding git repository.

That means running CLI in `project/src` directory would look up for `project/src/glagolica.toml` or `project/src/.config/glagolica.toml`.
If there's nothing found, it goes up and checks `project/glagolica.toml` and `project/.config/glagolica.toml`.
Then it checks the existence of `project/.git` directory and if there's one, it stops.

## Merging

Glagolica does not provide any functionality for merging 2 config files into one based on its location.
File `glagolica.toml` is unified and should be created only once in the project repository.
