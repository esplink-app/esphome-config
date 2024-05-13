# ESPHome Configuration Package for ESPLink Micro VPN

This repository contains ESPHome configuration packages for the [ESPLink Micro VPN](https://vpn.esplink.app).

To setup ESPLink on your ESPHome based microcontroller, add the following to your microcontroller's ESPHome yaml file:

```config.yaml
# Set secret private key
substitutions:
  esplink_microvpn_privatekey: !secret esplink_microvpn_privatekey
  esplink_microvpn_address: "Replace with Allowed Address from ESPLink dashboard"

# Pull in ESPLink configuration
packages:
  esplink: github://esplink-app/esphome-config/dev.yaml@main
```

Make sure to set the `esplink_microvpn_privatekey` secret in your ESPHome secrets.yaml and to copy the "Allowed Address" from your [ESPLink dashboard](https://vpn.esplink.app/dashboard). 

# Setting the Private Key (Placeholder; will become easier)

Run `wg genkey` to generate a private key and `wg pubkey` to generate a public key. Set your private key in your secrets.yaml like follows:

```secrets.yaml
esplink_microvpn_privatekey: "Replace with your private key"
```

Set your public key as the public key for your Link on your [ESPLink dashboard](https://vpn.esplink.app/dashboard).
