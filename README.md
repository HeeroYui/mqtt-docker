mqtt-docker
===========

Repository for wrapping `eclipse-mosquitto` to be used together with `docker-compose`.

In basis it have a config that open not secured MQTT over TCP and Websocket
It disable the anonimous user
It allow 2 user:
* user1 : MyPassword
* user2 : mYpASSWORD

The default port are:
* 1883: TCP
* 8883: SSL TCP
* 9001: Websocket
* 9002: SSL Websocket

License
=======

MPL-2

Clone the repository:
=====================

```
git clone https://github.com/HeeroYui/mqtt-docker.git
cd mqtt-docker
```

Compose and start your environement:
====================================

```
docker-compose up
```

If you prever do it in a deamon:

```
docker-compose -d up
```

Remove the current docker when started:

```
docker-compose rm mqtt
```


Create your password file, see documentation: ```https://mosquitto.org/man/mosquitto_passwd-1.html``` or update the file : ```config/passwd_readable```

and execute:
```
cd config
cp passwd_readable passwd
mosquitto_passwd -U passwd
cd ..
```


current config port:

      - "1883:1883"
      - "8883:8883"
      - "9001:9001"
      - "9002:9002"
