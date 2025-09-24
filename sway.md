# Sway

The key-bindings are very customizable and defined in the config file in `~/.config/sway/config`, so I won't duplicate that here. Instead, these are commands needed to do certain things that aren't immediately accessible in the UI.

## Bluetooth

Use `bluetoothctl` or `blueman-manager`.

To list available devices:

```
bluetoothctl devices
```

To pair with a device:

```
bluetoothctl pair 88:08:94:02:7C:12
```

where you should replace `88:08:94:02:7C:12` with the address that appears in the list displayed by `bluetoothctl devices`.

Once you've paired with a device once, you can connect to it with:

```
bluetoothctl connect 88:08:94:02:7C:12
```

where you should replace `88:08:94:02:7C:12` with the address that appears in the list displayed by `bluetoothctl devices`.

## Screenshots

```
grim -g "$(slurp)"
```

This saves a file to `~/Pictures` by default.

More at [Screenshots in Sway | Kai Breucker](https://kaibreucker.dev/en/content/foss/sway/screenshots/).


## WiFi 

Use `nmtui`.

