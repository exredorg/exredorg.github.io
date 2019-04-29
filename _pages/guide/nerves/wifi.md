---
title: Configuring Wifi
layout: single
permalink: /guide/nerves/wifi/
---

You can configure wifi access the usual way by setting the nerves network environment variables and rebuilding the firmware but if you are using the release image from github then you probably want an easier method.

There is a way to dynamically configure the wifi settings if you have console access (wired Ethernet or serial tty) to the running Exred Nerves system.

1. Create the `/root/wlan_config.yaml` file with the following content (replace _myssid_ and _mypassword_)

        nerves_network_ssid: myssid
        nerves_network_psk: mypassword

    You can create this on your host computer and ftp it to the Pi or you can log into your running Exred Nerves system and create the file by running `Fw.ExredConfigProvider.create_config/2`:

        iex(1)> Fw.ExredConfigProvider.create_config("myssid", "mypassword")

2. Reboot your Nerves system

The created YAML config file is read during Shoehorn init and the wifi settings are configured before the nerves network application starts up.