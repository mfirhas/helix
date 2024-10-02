# Configuration

To override global configuration parameters, create a `config.toml` file located in your config directory:

- Linux and Mac: `~/.config/helix/config.toml`
- Windows: `%AppData%\helix\config.toml`

> 💡 You can easily open the config file by typing `:config-open` within Helix normal mode.

Example config:

```toml
theme = "onedark"

[editor]
line-number = "relative"
mouse = false

[editor.cursor-shape]
insert = "bar"
normal = "block"
select = "underline"

[editor.file-picker]
hidden = false
```

You can use a custom configuration file by specifying it with the `-c` or
`--config` command line argument, for example `hx -c path/to/custom-config.toml`.
Additionally, you can reload the configuration file by sending the USR1
signal to the Helix process on Unix operating systems, such as by using the command `pkill -USR1 hx`.

Finally, you can have a `config.toml` local to a project by putting it under a `.helix` directory in your repository.
Its settings will be merged with the configuration directory `config.toml` and the built-in configuration.

### `[editor.explorer]` Section

Sets explorer side width and style.

| Key            | Description                                 | Default |
| -------------- | ------------------------------------------- | ------- |
| `column-width` | explorer side width                         | 30      |
| `position`     | explorer widget position, `left` or `right` | `left`  |
| `ignore-list`  | list of files/folders to be hidden from explorer tree view<br/> append `/` for folders | [".DS_Store", ".git/"] |
