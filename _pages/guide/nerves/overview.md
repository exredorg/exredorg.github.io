---
title: Exred Nerves Overview
layout: single
permalink: /guide/nerves/overview/
---

Installation
-------------
See the [Getting Started](/guide/getting-started/installation/) page.


Differences compared to Non-Nerves deployment
---------------------------------------------
### Sqlite backend
The Nerves version of Exred uses Sqlite3 as the database back-end as opposed to PostgreSQL in the non-nerves version.
A default demo database is part of the image. Since this is included with the firmware it ends up on a read-only partition.  
To make it usable for the system this default database file (`/var/exred_data/exred.sqlite3`) is copied to the read/write partition to `/root/data/exred.sqlite3` during the Shoehorn init process.
If you want to back up your flows you can copy the database file to a safe location (eg. download it through an ftp connection).
You can also revert to the demo database by deleting the live file (`/root/data/exred.sqlite3`) and rebooting the system.

### No gRPC support
The gRPC nodes [exred_node_grpc_server](https://github.com/exredorg/exred_node_grpc_server.git) and [exred_node_grpc_twin](https://github.com/exredorg/exred_node_grpc_server.git) need HTML2 support but the Phoenix and Cowboy versions used by the [exred_ui](https://github.com/exredorg/exred_ui.git) application conflict with this.  
On Nerves all the Exred nodes, the UI and other backend applications run in the same Erlang node therefore there can be no dependency conflict between them.  
The docker deployment runs the UI in a separate container so this conflict is not a problem there.  
If you need the gRPC support use the docker containers built for RPI3 (see [Getting Started](/guide/getting-started/installation/)).  
This will be resolved with upgrading the UI application to the latest Phoenix version.

### Hardcoded file names for AWS certs and private key:
If you are using the AWS IOT nodes to connect to the AWS IOT cloud these are the default config settings in the firmware release image:

    config :exred_node_aws_iot_daemon, :ssl,
      keyfile: "/root/data/private.pem.key",
      certfile: "/root/data/certificate.pem.crt",
      cacertfile: "/root/data/ca_root.pem"