---
title: AWS IoT Daemon
layout: single
---

A daemon node that sets up a connection to the AWS IoT service.

### Setup in AWS IoT Cloud

It needs a device (thing) set up in the AWS cloud per the instructions here: [AWS IOT Getting Started](https://docs.aws.amazon.com/iot/latest/developerguide/iot-gs.html){:target="\_blank"}

Proper certificates need to be generate and attached to the Thing and policies 
set up so that this node can access the Thing Shadow using the certs and private key.

The cert, private key and CA cert needs to be downloaded from AWS and placed somewhere in the 
local file system where the Elixir runtime can access it.

Configure these locations in the application config file.

Example: 

```elixir
# ssl options for the MQTT client
# these get passed to the Erlang ssl module
# see ssl_option() here: http://erlang.org/doc/man/ssl.html
config :exred_node_aws_iot_daemon, :ssl,
  keyfile: "/exred_data/certs/private.pem.key",
  certfile: "/exred_data/certs/certificate.pem.crt",
  cacertfile: "/exred_data/certs/symantec_ca_root.pem"
```

### Node Configuration

|Param.|Description|
|-----+-----|
|**host**| AWS IoT endpoint for MQTT connections; see:[AWS IoT](https://docs.aws.amazon.com/general/latest/gr/rande.html#iot_region){:target="\_blank"}|
|**port**| MQTT connection port|
|**client_id**| client id provided to the MQTT client (can be any string identifying this client)|

