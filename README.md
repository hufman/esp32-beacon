MK114 Bluetooth Beacon Monitor
==============================

Inspired by [this guide](https://www.reddit.com/r/homeautomation/comments/gcgim4/cross_post_im_tracking_my_cats_location_within_my/), I found the ESP32-based [MokoSmart MK114](https://www.mokosmart.com/smart-home-wifi-plug-mk114/) smart plug as the basis for my installation.

Here is the basic layout for my ESPHome.io configuration for flashing these devices, perhaps others may find it useful.

Besides the basic ESP32 BLE configuration, the `includes/mk114.yaml` file wires up the button to toggle the power output relay, and also exposes the LED as an RGB light for Home Assistant, with a temporary red or green transition when toggling the relay.

ESPHome does not support the RN8209C energy monitoring chip yet, so that feature is unavailable.

Example Flash Command
---------------------

`docker run --rm -v "${PWD}":/config --device=/dev/ttyUSB0 -it esphome/esphome mk114_1.yaml run`
