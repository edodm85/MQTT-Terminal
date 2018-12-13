# MQTT Terminal

<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/img1.png" width="150">

## What is MQTT Terminal?

MQTT Terminal is a MQTT Client for Androi with the possible to create multiple connections.

You can download from Google Play here:
* [MQTT Terminal FREE](https://play.google.com/store/apps/details?id=com.edodm85.mqttterminal.free)
* [MQTT Terminal (without ADS)](https://play.google.com/store/apps/details?id=com.edodm85.mqttterminal.paid)


## Features

- Multiple connections
- Send/Receive text or images
- Username and password (optional)
- Subscribe to topic (wildcards supported)
- Enable/Disable notifications for the topic

## Example

You can found this example "Send temperature value over MQTT protocol with mbed" [HERE](https://os.mbed.com/users/edodm85/notebook/mqtt-project-send-temperature-value-over-mqtt-prot/)



## How does it work?

1. Open the "MQTT Terminal" Application and create a new connection with the Broker informations.

<p align="left">
<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/screen1.png" width="300">
<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/screen2.png" width="300">
</p>

2. Open the new connection and insert a new topic (wildcards are accepted)

<p align="left">
<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/screen3.png" width="300">
<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/screen4.png" width="300">
</p>


3. Now you can receive/send text or images

<p align="left">
<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/screen5.png" width="300">
<img src="https://github.com/edodm85/MQTT-Terminal/blob/master/Resources/screen6.png" width="300">
</p>



## Send image from other clients

For receive images with my App you need to follow these two steps:

1. First, send this string: image_ + (bytes image)

2. Second send the image bytes


Example:

```
ByteArrayOutputStream stream = new ByteArrayOutputStream();
Bitmap image = ...
image.compress(Bitmap.CompressFormat.PNG, 80, stream);
byte[] byteArray = stream.toByteArray();
int len = byteArray.length;

oServiceConnection.publish(topic, "image_" + len);
oServiceConnection.publish(topic, byteArray);
```


## License

> Copyright (C) 2018 edodm85.  
> Licensed under the MIT license.  
> (See the [LICENSE](https://github.com/edodm85/MQTT-Terminal/blob/master/LICENSE) file for the whole license text.)
