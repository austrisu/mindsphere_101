# mindsphere_101

This is the repository containing 'virtual' sensors in facotry. There is simple visualization of facory line and all sensor data is sent to local MQTT brocker, from ehere enyone in local network can acces it (depends on your PC configuration also) and from there send data to Mindsphere using NodeRed mindsphere block.

## Node red dependencies

MQTT  broker - https://flows.nodered.org/node/node-red-contrib-mqtt-broker

## Setting up test factory

Import in to node-red `Factory simulation_node red.json`, and everithing should be working. All the sensor data are generated randomly and simple SCADA is displayed in http://<hostIP>/ui . Also from there some simple manual control operations can be done.

### Hoe does it works?

```

+-------------------------------------------------------+
| Virtual factory                                       |
|                                                       |
|                                                       |
|                                                       |               +---------------------------------+
|                                                       |               |                                 |
|   +---------------+                                   |               |                                 |
|   |Sensor data    |                                   |               |                                 |
|   |generation     |                +--------------+   |               |                                 |
|   |               |   MQTT         |              |   |   MQTT        |                                 |
|   |  - pump speed +----------------> MQTT broker  +-------------------+                                 |
|   |  | flow speed |                |              |   |               |                                 |
|   |  - etc.       |                +--------------+   |               |                                 |
|   |               |                                   |               |                                 |
|   +---------------+                                   |               |                                 |
|                                                       |               +---------------------------------+
+-------------------------------------------------------+


```

## Mindsphere Onboarding

