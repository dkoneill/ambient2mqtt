Ambient2MQTT
============

The San Diego Rowing Club forked and modified this great piece of software
to modify a few MQTT parameters to match their long term data acquired
via the AmbientWeather.net API.

Patrick Wagstrom &lt;patrick@wagstrom.net&gt;

October 2021

Overview
---------

This is a simple single binary server that acts as a target for your Ambient Weather station on your local network and relays the data over MQTT so other IoT related devices can make use of it.

You will need to have a newer firmware installed for your Ambient Weather station in order to make use of this feature.

Usage
-----

```bash
./ambient2mqtt -config config.toml
```

Configuration
-------------

Configuration is done via a TOML file. Here's a simple example configuration:

```toml
[http]
    port = 2466

[mqtt]
    broker_host = "mqtt-broker.lan"
    broker_port = 1883
    broker_username = ""
    broker_password = ""
    client_id = "ambient2mqtt"
    topic_prefix = "weather"
    topic = "ws-2902"
[hass]
    discovery = true
    discovery_prefix = "homeassistant"
    object_id = "ws-2902a"

```

License
-------

Licensed under terms of the MIT license
