# BrewBench

<img src="img/brewbench-logo.png?raw=true" alt="BrewBench logo" title="BrewBench" align="right" />

Is an Arduino Yun brew monitor for the home brewer enthusiast that uses the Arduino REST API to interface with thermistors connected to the analog ports.

See [Thermistor](https://learn.adafruit.com/thermistor/using-a-thermistor) for wiring these up on analog ports.

## Setup the Arduino

* Connect it to your WiFi (see [ArduinoYun](https://www.arduino.cc/en/Guide/ArduinoYun#toc14))
* Enable the REST API (see [ArduinoYun](https://www.arduino.cc/en/Guide/ArduinoYun#toc5))
* Upload the [Arduino sketch](arduino/BrewBench/BrewBench.ino)

## Clone this repo and copy the code to your Arduino

```
# Add rsync to your Arduino
ssh root@arduino.local
opkg update
opkg install rsync
exit
```

```
# get the web code
git clone https://github.com/avantassel/brewbench
cd brewbench

# copy to your Arduino
rsync -rav -e ssh --delete --exclude-from '.rsyncignore' ./ root@arduino.local:/www/brewbench
```

## Development

```
npm install
gulp
```

## Open a browser

* [http://arduino.local/brewbench/](http://arduino.local/brewbench/)

<img src="img/screenshot-desktop.png?raw=true" alt="BrewBench screenshot" align="center" />

<img src="img/brewbench-wiredup.jpg?raw=true" alt="BrewBench wired up" align="center" />

## TODO
* Save settings to key/value data store on the Arduino
* Load settings from key/value data store on the Arduino
* Add option to post readings to a cloud based DB
* Add option to poll cloud based DB instead of the Arduino
* Add option to save readings to an SD card
* Add option to load readings from an SD card
* Add option to save a brew session
* Add option to load a brew session
* Add txt message alert option
