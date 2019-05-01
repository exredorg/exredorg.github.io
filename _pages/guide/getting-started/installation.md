---
title: Installation
layout: single
permalink: /guide/getting-started/installation/
---

Use Docker
------------

**On x86 (desktop)**

    git clone https://github.com/exredorg/exred-compose.git
    cd exred-compose
    docker-compose up
    
**On Raspberry Pi**

    git clone https://github.com/exredorg/exred-compose.git
    cd exred-compose
    docker-compose -f rpi-docker-compose.yml up

**Go to `http://localhost:4000` to access the UI.**


Nerves
--------
**NOTE: Exred Nerves runs on Raspberry Pi 3.**

Download the release image and write it to an SD card (change `of=/dev/sdb` to the correct device)

    wget https://github.com/exredorg/exred_nerves/releases/download/v0.1.1/exred_nerves_v0.1.1.img
    dd bs=4M if=exred_nerves_v0.1.1.img of=/dev/sdb 

**Go to `http://nerves.local:8080` to access the UI.**  
(you might have to use the actual IP instead of nerves.local)

This will work with a wired Ethernet connection and a [USB Serial Console](https://hexdocs.pm/nerves/faq.html#using-a-usb-serial-console).  
If you need wireless connection see instructions [here](/guide/nerves/wifi/).  
More Nerves specific info [here](/guide/nerves/overview).


Run From Source
---------------
You will need to set up and run two separate elixir applications and a postgresql server (and optionally a redis server).

1\. Set up a postgresql server and optionally create a user for exred

2\. Set up the Exred UI application

    git clone https://github.com/exredorg/exred_ui.git
    cd exred_ui
    mix deps.get
    iex -S mix phx.server


3\. Set up the Exred Scheduler application

    git clone https://github.com/exredorg/exred_scheduler.git
    cd exred_scheduler
    mix deps.get
    iex -S mix

    
If needed edit the config files for both applications before you start them.


Build a Release
---------------

    git clone https://github.com/exredorg/exred_ui.git
    cd exred_ui
    make release

    git clone https://github.com/exredorg/exred_scheduler.git
    cd exred_scheduler
    make release

Grab the release tar files. Unpack, edit config and run the releases.

