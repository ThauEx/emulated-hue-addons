# Emulated Hue Add-Ons (ThauEx fork)

Home Assistant add-on repository for [ThauEx/emulated-hue-core](https://github.com/ThauEx/emulated-hue-core), a fork of the (inactive) [hass-emulated-hue/core](https://github.com/hass-emulated-hue/core) that adds a direct ESPHome native-API path and CLIP v2 Entertainment support - see that repo's README for details on what's different and why.

## Install

In Home Assistant: Settings → Add-ons → Add-on Store → ⋮ → Repositories → add:

```
https://github.com/ThauEx/emulated-hue-addons
```

Then install **Emulated HUE (Direct ESPHome)**.

## Updating

The add-on's `version` field is pinned to a specific `emulated-hue-core` image tag (a full git commit SHA) rather than `latest`, so that Supervisor can detect and offer real updates instead of silently reusing an already-pulled image. Each new fix bumps this repo's `emulated_hue_direct/config.json` to the new tag - just click "Update" in the add-on's page when one shows up.
