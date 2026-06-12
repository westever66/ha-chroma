[![GitHub Release](https://img.shields.io/github/release/Vaskivskyi/ha-chroma.svg?style=for-the-badge&color=blue)](https://github.com/Vaskivskyi/ha-chroma/releases) [![License](https://img.shields.io/github/license/Vaskivskyi/ha-chroma.svg?style=for-the-badge&color=yellow)](https://github.com/Vaskivskyi/ha-chroma/blob/main/LICENSE) [![Community forum discussion](https://img.shields.io/badge/COMMUNITY-FORUM-success?style=for-the-badge&color=blue)](https://community.home-assistant.io/t/custom-component-chroma-integration-control-your-rgb/464511) [![Installations](https://img.shields.io/endpoint?url=https://vaskivskyi.github.io/ha-custom-analytics/badges/chroma/total.json&style=for-the-badge&color=yellow)](https://github.com/Vaskivskyi/ha-custom-analytics)

## Chroma LAN fork

This fork is maintained for controlling a Windows Razer Chroma SDK instance from a Home Assistant server running on another LAN machine. It adds a configurable SDK port and uses the session `uri` returned by the SDK/proxy.

For the current LAN proxy setup, use:
- Host: `192.168.0.52`
- Port: `15435`

## Control your Chroma-enabled devices from Home Assistant

`Chroma LAN` is a custom integration for Home Assistant to control your Razer Chroma-enabled devices using the [forked AIOChroma](https://github.com/westever66/aiochroma) python library.

Please, refer to the GitHub [Readme](https://github.com/westever66/ha-chroma/) for detailed information on the available sensors and controls.

A short presentation of the features can be found in this [YouTube video](https://www.youtube.com/watch?v=ytdS9JUWSb4).

## Installation

1. Click Install
2. Restart Home Assistant
3. In the Home Assistant UI:
   `Configuration -> Devices & Services -> Integrations -> Add integration -> Chroma`

## Usage

To connect you need to provide the following data:
- IP address or hostname
- SDK port
- Which devices do you want to control (e.g. `chromalink`, `headset`, `keyboard`, `keypad`, `mouse`, `mousepad`)
- Layout of your keyboard (if the `keyboard` option is selected)

#### Allow the connection (adjust your firewall settings)

When using the LAN proxy, allow incoming `TCP` connections from the Home Assistant machine to the proxy entry port, for example `15435`, and to the session ports allocated by the proxy, for example `15436+`.

#### Lights

The integration provides a light entity per each device selected during the configuration process. Every entity supports `rgb_color` and `brightness` attributes.

#### Services

The `chroma.service_send_message` service allows sending any string message to your per-key RGB keyboard. The message will be displayed symbol by symbol. Please, refer to the [how-to documentation](https://github.com/westever66/ha-chroma/blob/dev/docs/how-to.md) for more details.

Currently, the following keyboard layouts are supported: `EN_US`.

You can still use the service if your keyboard layout is not yet supported. E.g. you can change your string from `Lazy fox was here` to `Layz fox was here` to properly be displayed with the German layout.

---

<a href="https://www.buymeacoffee.com/vaskivskyi" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-blue.png" alt="Buy Me A Coffee" style="height: 60px !important;"></a>
