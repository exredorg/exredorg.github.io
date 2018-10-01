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

Run From Source
---------------

    git clone https://github.com/exredorg/exred.git
    cd exred
    mix deps.get

Set up a postgresql server and optionally create a user for exred
    
Edit config files for the `exred_scheduler` and `exred_ui` apps. 

    iex -S mix phx.server


Build a Release
---------------

    git clone https://github.com/exredorg/exred
    cd exred
    mix deps.get deps.compile
    mix release

Grab the tar file from `rel/<version>/exred.tar.gz`  
Unpack anywhere  
Edit config in  
Run it: `./bin/exred start`

