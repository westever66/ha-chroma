# Chroma LAN

Personal fork of [`Vaskivskyi/ha-chroma`](https://github.com/Vaskivskyi/ha-chroma) for controlling a Windows Razer Chroma SDK instance from a Home Assistant server running on another LAN machine.

This fork adds:

- a configurable Chroma SDK port in the Home Assistant config flow;
- support for the session `uri` returned by the Chroma SDK or LAN proxy through the forked [`westever66/aiochroma`](https://github.com/westever66/aiochroma);
- a HACS dependency pinned to the forked `aiochroma` `dev` branch.

## Current LAN Proxy Setup

Use these values when adding the integration:

- Host: `192.168.0.52`
- Port: `15435`

The proxy should be reachable from the Home Assistant machine on the entry port, for example `15435`, and on the session ports it allocates, for example `15436+`.

## HACS

Add this repository as a HACS custom repository:

```text
https://github.com/westever66/ha-chroma
```

Category: `Integration`

After installing or updating, restart Home Assistant and add the `Chroma LAN` integration from Devices & Services.

## Notes

The integration domain remains `chroma`, so Home Assistant installs it under `custom_components/chroma`.

This fork is for local personal use. For upstream documentation and device support details, see the original project:

```text
https://github.com/Vaskivskyi/ha-chroma
```
