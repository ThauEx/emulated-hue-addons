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

## Direct ESPHome path

Stop the add-on, edit `emulated_hue.json` in `/config/hass-emulated-hue/`,
and add to the relevant light's entry under `"lights"`:

```json
"esphome_host": "192.168.178.151",
"esphome_port": 6053,
"esphome_password": "220190"
```

`esphome_port` and `esphome_password` are optional (default port 6053, no
password). Restart the add-on afterwards.
