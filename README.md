# ESPHome configuration

![ESPHome_logo]

My current configuration for all devices based on [ESPHome].

## Common firmware features

The following features are implemented for every device

- [Wifi] with failover [Access Point Mode] and [Captive Portal]
- [Over The Air] firware updates
- [Native API] connection for [Home Assistant]
- [Web Server] based device control
- [Time] synchronization with [Home Assistant]
- [Status Binary Sensor] (device status)
- [Wifi Signal Sensor]
- [Uptime Sensor]
- [Restart Switch]

## Device types

| Device  | Type  | Description |
| -- |  --  | --  |
| [blitzwolf_bw_rc1]  | [Blitzwolf BW-RC1]        | IR Controller             |
| [diy_hue]           | [DIY Hue]                 | Hue compatible DIY light  |
| [gosund_sp111]      | [Gosund SP111]            | Power Monitoring Plug     |
| [koogeek_kloe4]     | [Koogeek KLOE4]           | Power Strip               |
| [shelly_1pm]        | [Shelly 1PM]              | Power Monitoring Relay    |
| [sonoff_basic]      | [Sonoff Basic]            | Relay                     |
| [sonoff_s20]        | [Sonoff S20]              | Power Plug                |
| [tuya_qs_d02]       | [Tuya QS-WiFi-D02-TRIAC]  | 2 Channel Dimmer          |
| [ventilation]       | [Sonoff TH10]             | Humidity controlled Relay |

## Device specific firmware features

| Device  | [Platform]  | [Physical Button]  | [Status LED] | [Relay] | [UART] | [Light] | [Remote Transmitter]
| --  |  :--: |  :--:  | :--:  |  :--: |  :--: |  :--: |  :--: |
| [blitzwolf_bw_rc1]  | [ESP8266] | -  | x |  - |  - | -               | [ir_receiver] |
| [diy_hue]           | [ESP8266] | -  | x |  - |  - | [FastLED]       | - |
| [gosund_sp111]      | [ESP8266] | x  | x |  x |  - | -               | - |
| [koogeek_kloe4]     | [ESP8266] | x  | x |  x |  - | -               | - |
| [shelly_1pm]        | [ESP8266] | x  | x |  x |  - | -               | - |
| [sonoff_basic]      | [ESP8266] | x  | x |  x |  - | -               | - |
| [sonoff_s20]        | [ESP8266] | x  | x |  x |  - | -               | - |
| [tuya_qs_d02]       | [ESP8266] | -  | - |  - |  x | [Monochromatic] | - |
| [ventilation]       | [ESP8266] | x  | x |  x |  - | -               | - |

## Device specific sensors

| Device  | [HLW8012]  | [Remote Receiver] |  [DHT] | Features
| --  |  :--: |  :--: |  :--: | --  |
| [blitzwolf_bw_rc1]  | - | x | - | [ir_transmitter] |
| [shelly_1pm]        | x | - | - | current, power, [total_daily_energy] |
| [gosund_sp111]      | x | - | - | current, power, voltage, [total_daily_energy] |
| [ventilation]       | - | - | SI7021 | temperature, humidity |

[DIY Hue]: https://diyhue.org/
[ESPHome]: https://esphome.io/
[ESPHome_logo]: https://esphome.io/_images/logo-text.svg
[Home Assistant]: https://www.home-assistant.io/
[Blitzwolf BW-RC1]: https://www.blitzwolf.com/BlitzWolf%C2%A0BW-RC1-WiFi-Smart-IR-Controller-with-360%C2%B0-Transmission,-APP-Control,-Works-with-Alexa,-Automatic-Identification,-DIY-Pairing-and-Slim-Design-p-409.html
[Gosund SP111]: https://www.gosund.com/download/smart_plug/126.html
[Koogeek KLOE4]: https://www.koogeek.com/p-kloe4.html
[Shelly 1PM]: https://shelly.cloud/products/shelly-1pm-smart-home-automation-relay/
[Sonoff Basic]: https://sonoff.tech/product/wifi-diy-smart-switches/basicr2
[Sonoff S20]: https://sonoff.tech/product/wifi-smart-plugs/s20
[Sonoff TH10]: https://sonoff.tech/product/wifi-diy-smart-switches/th10-th16
[Tuya QS-WiFi-D02-TRIAC]: https://expo.tuya.com/product/373634s
[Access Point Mode]: https://esphome.io/components/wifi.html#access-point-mode
[Board]: https://esphome.io/components/status_led.html
[Captive Portal]: https://esphome.io/components/captive_portal.html
[DHT]: https://esphome.io/components/sensor/dht.html
[ESP8266]: https://esphome.io/devices/esp8266.html
[FastLED]: https://esphome.io/components/light/fastled.html
[HLW8012]: https://esphome.io/components/sensor/hlw8012.html
[Light]: https://esphome.io/components/light.html
[Native API]: https://esphome.io/components/api.html
[Monochromatic]: https://esphome.io/components/light/monochromatic.html
[Over The Air]: https://esphome.io/components/ota.html
[Physical Button]: https://esphome.io/components/binary_sensor/gpio.html
[Platform]: https://esphome.io/components/status_led.html
[Relay]: https://esphome.io/cookbook/relay.html
[Remote Receiver]: https://esphome.io/components/remote_receiver.html
[Remote Transmitter]: https://esphome.io/components/remote_transmitter.html
[Restart Switch]: https://esphome.io/components/switch/restart.html
[Status Binary Sensor]: https://esphome.io/components/binary_sensor/status.html
[Status LED]: https://esphome.io/components/status_led.html
[Time]: https://esphome.io/components/time.html
[UART]: https://esphome.io/components/uart.html
[Uptime Sensor]: https://esphome.io/components/sensor/uptime.html
[Web Server]: https://esphome.io/components/web_server.html
[Wifi]: https://esphome.io/components/wifi.html
[Wifi Signal Sensor]: https://esphome.io/components/sensor/wifi_signal.html
[blitzwolf_bw_rc1]: https://github.com/ImEmJay/esphome-config/blob/master/blitzwolf_bw_rc1_01.yml
[diy_hue]: https://github.com/ImEmJay/esphome-config/blob/master/diy_hue_01.yml
[gosund_sp111]: https://github.com/ImEmJay/esphome-config/blob/master/gosund_sp111_01.yml
[koogeek_kloe4]: https://github.com/ImEmJay/esphome-config/blob/master/koogeek_kloe4_01.yml
[ir_receiver]: https://github.com/ImEmJay/esphome-config/blob/master/common/remote_receiver/ir_receiver.yaml
[ir_transmitter]: https://github.com/ImEmJay/esphome-config/blob/master/common/remote_transmitter/ir_transmitter.yaml
[light_id]: https://github.com/ImEmJay/esphome-config/blob/master/common/text_sensor/light_id.yaml
[shelly_1pm]: https://github.com/ImEmJay/esphome-config/blob/master/shelly_1pm_01.yml
[sonoff_basic]: https://github.com/ImEmJay/esphome-config/blob/master/sonoff_basic_01.yml
[sonoff_s20]: https://github.com/ImEmJay/esphome-config/blob/master/sonoff_s20_01.yml
[gosund_sp111]: https://github.com/ImEmJay/esphome-config/blob/master/gosund_sp111_01.yml
[total_daily_energy]: https://github.com/ImEmJay/esphome-config/blob/master/common/sensor/total_daily_energy.yaml
[tuya_qs_d02]: https://github.com/ImEmJay/esphome-config/blob/master/tuya_qs_d02_01.yml
[ventilation]: https://github.com/ImEmJay/esphome-config/blob/master/ventilation.yml
