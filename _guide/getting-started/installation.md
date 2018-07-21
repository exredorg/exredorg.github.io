---
title: Installation
layout: single
---

Using Docker
------------

    curl {{site.url}}{{site.baseurl}}/assets/downloads/docker-compose.yml | docker-compose -f - up


Run From Source
---------------

    git clone https://github.com/exredorg/exred
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


{% assign download_files = site.static_files | where: "download", true %}
{% for df in download_files %}
  {{site.url}}{{site.baseurl}}{{ df.path }}
{% endfor %}


