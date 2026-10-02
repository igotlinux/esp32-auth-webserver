# esp32 web server

i wrote this because standing up to flick a light switch is too much physical activity for a software engineer

you run this on an esp32 with micropython and it hosts a web page with basic auth so random people on your wifi cannot flicker your lights while you sleep

## what you need

an esp32 board
micropython flashed on it
ampy or whatever tool you use to push files
wifi credentials

## how to run

1 clone the repo
```bash
git clone https://github.com/igotlinux/esp32-auth-webserver.git
cd esp32-auth-webserver
```

2 set your wifi details in networkcredentials py
```python
ssid = "your wifi name"
password = "your wifi password"
```

3 push files to the board
```bash
ampy --port /dev/ttyUSB0 put networkcredentials.py
ampy --port /dev/ttyUSB0 put main.py
```

4 reboot the board check the serial console for the ip address open that ip in any browser and toggle the pin

## why this exists

practical demo of microdot socket handling and minimal memory footprint on embedded chips without running heavy frameworks

## license

mit
