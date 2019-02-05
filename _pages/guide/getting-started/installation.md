---
title: Installation
layout: single
permalink: /guide/getting-started/installation/
---

Using Docker
------------

    git clone https://github.com/exredorg/exred-compose.git
    cd exred-compose
    docker-compose up
    
**Go to 'http://localhost:4000' to access the UI.**

Run From Source
---------------
You will need to set up and run two separate elixir applications and a postgresql server (and optionally a redis server).

1. Set up a postgresql server and optionally create a user for exred

2. Set up the Exred UI application

        git clone https://github.com/exredorg/exred_ui.git
        cd exred_ui
        mix deps.get
        iex -S mix phx.server


3. Set up the Exred Scheduler application

        git clone https://github.com/exredorg/exred_scheduler.git
        cd exred_scheduler
        mix deps.get
        iex -S mix

    
Edit the config files for both applications if needed before you start them.


Build a Release
---------------

    git clone https://github.com/exredorg/exred_ui.git
    cd exred_ui
    make release

    git clone https://github.com/exredorg/exred_scheduler.git
    cd exred_scheduler
    make release

Grab the release tar files. Unpack, edit config and run the releases.

