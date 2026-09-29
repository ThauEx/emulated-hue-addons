# Emulated Hue (Direct ESPHome)

Fork of [Emulated Hue](https://github.com/hass-emulated-hue/core) with direct
native-control paths (ESPHome, WiZ) for Entertainment (Ambilight-style)
streaming. Lights without a direct-path target configured behave exactly
like upstream, going through Home Assistant as usual.

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

## Direct-path light configuration

Everything else - assigning a light to ESPHome or WiZ, its host/port/credential,
and triggering pairing mode - is done from the add-on's own panel, not here.
Enable "Show in sidebar" on this add-on's Info page, then open it from the
Home Assistant sidebar. Changes there take effect immediately, no restart
needed. See the main [README](https://github.com/ThauEx/emulated-hue-core#direct-path-light-configuration)
for details.
