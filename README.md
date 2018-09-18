# nodejs_mqtt_socketio
Express based web application to show sensor data coming from remote MQTT broker.

## Table of Contents
 - [Installation](#installation)
 - [Configuration](#configuration)
 - [Usage](#usage)
 - [Contributing](#contributing)
 - [References](#references)

## Installation

First of all install the required packages:
```shell
 $ npm install
```

## Configuration

1. Rename "server.js.sample" to "server.js":
```shell
 $ mv server.js.sample server.js
```

2. Edit the server.js file according to your deployment:
```javascript
// In case of MQTTS (TLS):
 var connectOptions = {
     host: "<MQTT_server_IP_or_hostname>",
     port: 8883,
     protocol: "mqtts",
     keepalive: 10,
     clientId: "test_client_01",
     protocolId: "MQTT",
     protocolVersion: 4,
     clean: true,
     reconnectPeriod: 2000,
     connectTimeout: 2000,
     cert: fs.readFileSync("ca.crt"),
     rejectUnauthorized: false,
};

// In case of MQTT:
var connectOptions = {
    host: "<MQTT_server_IP_or_hostname>",
    port: 1883,
    protocol: "mqtt",
    keepalive: 10,
    clientId: "test_client_01",
    protocolId: "MQTT",
    protocolVersion: 4,
    clean: true,
    reconnectPeriod: 2000,
    connectTimeout: 2000
};

var topic="<topic_to_subscribe>";
```

## Usage

Run the backend:
```shell
 $ npm start
```
Then, open a web browser and type the following URL: localhost:4200
In case that the client is connected from a remote host, modify the "public/index.html" file in order to set your backend IP settings.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## References
