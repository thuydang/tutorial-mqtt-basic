## Quick start

### Make sure mosquitto.conf file has correct configuration:

Listen on all interfaces (default is 127.0.0.1 and can't be accessed from container network).
    
    bind_address 0.0.0.0

Anonymous user
    
    allow_anonymous true


### Start docker container for eclipse mosquitto MQTT broker:

    docker-compose -f docker-compose-mqtt.yml up

### Start an MQTT Client, e.g., MQTTBox https://chrome.google.com/webstore/detail/mqttbox/kaajoficamnjijhkeomgfljpicifbkaf

Configure connection as below:

```
MQTT Client Name: Example
MQTT Client Id: Auto generated
Append timestamp to MQTT client id? Yes
Broker is MQTT v3.1.1 compliant? Yes
Protocol: mqtt / tcp
Host: 127.0.0.1:1883
Clean Session? Yes
Auto connect on app launch? Yes
Username: mqtt
Password: mqtt
Reschedule Pings? Yes
Queue outgoing QoS zero messages? Yes
Reconnect Period (milliseconds) 
Connect Timeout (milliseconds) 
KeepAlive (seconds) 
Will - Topic 
Will - QoS: 0 - Almost Once
Will - Retain: No
Will - Payload: 
```
![Configure Connection](./docs/media/Screenshot%20from%202021-12-09%2014-27-27.png)

Configure Publisher as shown below:

Topic to publish: /my/topic
```
QoS: 0 - Almost Once
Retain: 
Payload Type: Strings / JSON / XML / Characters
e.g: {'hello':'world'}
Payload: {'hello':'world'}
```

Configure Subscriber as shown below:

```
Topic to subscribe: /my/topic   (use /# to subscribe to all topic). 
QoS: 0 - Almost Once
```

![Configure Pub/Sub](./docs/media/Screenshot%20from%202021-12-09%2014-17-53.png)

## More resources

- Install Mosquitto: https://www.digitalocean.com/community/tutorials/how-to-install-and-secure-the-mosquitto-mqtt-messaging-broker-on-ubuntu-16-04
- Secure MQTT, forwarding, etc.

