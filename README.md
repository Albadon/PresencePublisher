# Presence Publisher

[<img src="https://f-droid.org/badge/get-it-on.png" alt="Get it on F-Droid" height="75">](https://f-droid.org/packages/org.ostrya.presencepublisher)

A simple app that regularly publishes to a configurable MQTT topic whenever connected to a given WiFi network.
This can be used to integrate the presence of your phone in home automation.

The app uses the built-in Android alarm manager, so notifications are sent even if the phone is in stand-by.

## TLS with self-signed certificates

The app uses the default Android CA trust store for checking the server certificate validity. You can simply add your
certificate via:

* Android 4.0 - 7.1:
  * `Settings` → `Security` → `Install from SD card`
* Android 8.0+:
  * `Settings` → `Security & location` → `Encryption & credentials` → `Install from SD card`

## Permissions

* ACCESS_COARSE_LOCATION: on Android 9+, necessary to retrieve SSID of connected WiFi (you do not need to grant
 the permission in Android 6.0 - 8.1 for the app to work)
* ACCESS_NETWORK_STATE: necessary to register network change listener
* ACCESS_WIFI_STATE: necessary to retrieve SSID of connected WiFi
* INTERNET: only necessary if your MQTT server is not running locally
* FOREGROUND_SERVICE: necessary to send notifications
* RECEIVE_BOOT_COMPLETED: necessary to start service on start-up

## Future ideas

* more conditions when to send notification
  * time ranges
  * presence of Bluetooth beacons
  * actual location
  * ...
* ...
