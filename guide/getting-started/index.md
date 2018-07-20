---
title: Exred Overview
layout: single
classes:
- wide
sidebar:
  nav: guide_docs
---

Exred is a flow-based programming tool. It's basically a [Node-RED](https://nodered.org/) clone with an Elixir twist. You don't have to know Elixir to use it although that is definitely helpful.

Exred utilises Elixir's (actually Erlang's) easy process creation, message passing and supervision trees.

It can be deployed anywhere where you can run an Erlang release or a Docker image.  
There are docker files to build images based on the standard ```elixir:1.5``` image (Debian) and on the ```resin/rpi-raspbian``` image.
Using the rpi image it can be run on a Raspberry Pi with Raspbian, Docker and Docker Compose installed.

Future plans include support for deployment with [Nerves](https://nerves-project.org/) 
