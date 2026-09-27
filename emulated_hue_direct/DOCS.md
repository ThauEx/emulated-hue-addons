# Emulated Hue (Direct ESPHome)

Fork of [Emulated Hue](https://github.com/hass-emulated-hue/core) with a
direct ESPHome native-API path for Entertainment (Ambilight-style) streaming.
Lights without `esphome_host` set in their light config behave exactly like
upstream, going through Home Assistant as usual.

## Configuration Options

### Option: `http_port`

Enter an integer to specify a custom http port. Defaults to port 80 if not specified.

### Option: `https_port`

Enter an integer to specify a custom https port. Defaults to port 443 if not specified.

### Option: `use_default_ports_for_discovery`

Only use HTTP and HTTPS ports for server listening, but continue to advertise HUE on 80 and 443.
Useful for reverse proxies.

### Option: `verbose`

Enter true or false to toggle verbose logging.

### Option: `esphome_host`

IP or hostname of an ESPHome device to use as the default for the direct
entertainment path (see below). Leave empty to disable it.

### Option: `esphome_port`

Native API port of that ESPHome device. Defaults to 6053 (ESPHome's default).

### Option: `esphome_password`

Native API password of that ESPHome device (the `password:` under `api:` in
its YAML), if it has one.

## Direct ESPHome path

The `esphome_*` options above apply to any light that doesn't set its own
`esphome_host`, which covers the common case of a single ESPHome light. For
more than one, stop the add-on, edit `emulated_hue.json` in
`/config/hass-emulated-hue/`, and add to each light's entry under `"lights"`:

```json
"esphome_host": "192.168.178.151",
"esphome_port": 6053,
"esphome_password": "220190"
```

A light's own `esphome_host` always overrides the add-on-wide default.
