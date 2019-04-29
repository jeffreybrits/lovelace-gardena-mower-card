# gardena-mower-card

Simple card for Gardena robotmower in Home Assistant's Lovelace UI

[![GH-release](https://img.shields.io/badge/version-0.1-red.svg?style=flat-square)](https://raw.githubusercontent.com/benct/lovelace-xiaomi-vacuum-card/master/xiaomi-vacuum-card.js)
[![GH-last-commit](https://img.shields.io/github/last-commit/benct/lovelace-xiaomi-vacuum-card.svg?style=flat-square)](https://github.com/benct/lovelace-xiaomi-vacuum-card/commits/master)
[![GH-code-size](https://img.shields.io/github/languages/code-size/benct/lovelace-xiaomi-vacuum-card.svg?style=flat-square)](https://github.com/benct/lovelace-xiaomi-vacuum-card)

### Setup

Add [gardena-mower-card.js](https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/gardena-mower-card.js) to your `<config>/www/` folder. Add the following to your `ui-lovelace.yaml` file:

```yaml
resources:
  - url: /local/gardena-mower-card.js?v=0.1
    type: js
```
If you want to use the mower background image, add [img/mower.png](https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/img/mower.png) to `<config>/www/img/`.

### *(Optional)* Add to custom updater

1. Make sure you have the [custom_updater](https://github.com/custom-components/custom_updater) component installed and working.

2. Add a new reference under `card_urls` in your `custom_updater` configuration in `configuration.yaml`.

```yaml
custom_updater:
  card_urls:
    - https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/tracker.json
```

### Options

| Name | Type | Default | Description
| ---- | ---- | ------- | -----------
| type | string | **Required** | `custom:gardena-mower-card`
| entity | string | **Required** | `vacuum.my_gardena_mower`
| name | string/bool | `friendly_name` | Override entity friendly name (set to false to hide title)
| background | string/bool | `img/mower.png` | Custom path/name of background image (set to false to disable background)
| buttons | bool | `true` | Set to false to hide button row
| vendor | string | gardena | Set to ecovacs to use with ecovacs

### Examples

![gardena-mower-card](https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/examples/default.png)

Hidden title/name

![gardena-mower-card-no-title](https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/examples/no-title.png)

Hidden button row

![gardena-mower-card-no-buttons](https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/examples/no-buttons.png)

No background image

![gardena-mower-card-no-background](https://raw.githubusercontent.com/Cavemanz/lovelace-gardena-mower-card/master/examples/no-background.png)

```yaml
- type: custom:gardena-mower-card
  entity: vacuum.gardena-mower_cleaner
  background: custom/folder/and/file.png
  name: Gardena Mower
  buttons: false
```


### Disclaimer

This project is not affiliated, associated, authorized, endorsed by, or in any way officially connected with Gardena, or any of its subsidiaries or its affiliates. The official Gardena website can be found at https://www.gardena.com/.
