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
| [bathroom_sensor]   | DIY                       | Multi-sensor node                                           |
| [blitzwolf_bw_rc1]  | [Blitzwolf BW-RC1]        | IR Controller                                               |
| [diy_hue]           | [DIY Hue]                 | Hue compatible DIY light                                    |
| [gosund_sp111]      | [Gosund SP111]            | Power Monitoring Plug                                       |
| [koogeek_kloe4]     | [Koogeek KLOE4]           | Power Strip                                                 |
| [room_sensor]       | DIY                    | Multi-sensor node                                           |
| [shelly_1_light]    | [Shelly 1]                | Relay based light                                           |
| [shelly_1pm]        | [Shelly 1PM]              | Power Monitoring Relay                                      |
| [shelly_2_5_light]  | [Shelly 2.5]              | 2 Channel Light Relay with temperature and power monitoring |
| [sonoff_basic]      | [Sonoff Basic]            | Relay                                                       |
| [sonoff_s20]        | [Sonoff S20]              | Power Plug                                                  |
| [tuya_qs_d02]       | [Tuya QS-WiFi-D02-TRIAC]  | 2 Channel Dimmer                                            |
| [ventilation]       | [Sonoff TH10]             | Humidity controlled Relay                                   |

## Device specific firmware features

| Device  | [Platform]  | [Physical Button]  | [Status LED] | [Relay] | [UART] | [Light] | [Remote Transmitter]
| --  |  :--: |  :--:  | :--:  |  :--: |  :--: |  :--: |  :--: |
| [bathroom_sensor]   | [ESP32]   | -  | x |  - |  - | -               | [Xiaomi Miscale] |
| [blitzwolf_bw_rc1]  | [ESP8266] | -  | x |  - |  - | -               | [ir_receiver] |
| [diy_hue]           | [ESP8266] | -  | x |  - |  - | [FastLED]       | - |
| [gosund_sp111]      | [ESP8266] | x  | x |  x |  - | -               | - |
| [koogeek_kloe4]     | [ESP8266] | x  | x |  x |  - | -               | - |
| [room_sensor]       | [ESP32]   | -  | x |  - |  - | -               | - |
| [shelly_1_light]    | [ESP8266] | -  | - |  x |  - | [Binary]        | - |
| [shelly_1pm]        | [ESP8266] | x  | x |  x |  - | -               | - |
| [shelly_2_5_light]  | [ESP8266] | x  | x |  x |  - | [Binary]        | - |
| [sonoff_basic]      | [ESP8266] | x  | x |  x |  - | -               | - |
| [sonoff_s20]        | [ESP8266] | x  | x |  x |  - | -               | - |
| [tuya_qs_d02]       | [ESP8266] | -  | - |  - |  x | [Monochromatic] | - |
| [ventilation]       | [ESP8266] | x  | x |  x |  - | -               | - |

## Device specific sensors

| Device  | [Remote Receiver] | [GPIO] |  [DHT]  | Power Sensor | [ADC] | [I²C] | Features
| --  |  :--: |  :--: |  :--: |  :--: |  :--: |  :--: | --  |
| [bathroom_sensor]   | x | x | - | - | - | [BME280] | temperature, humidity, pressure, [motion], [illuminance], [miband], [miband_rssi] |
| [blitzwolf_bw_rc1]  | x | - | - | - | - | - | [ir_transmitter] |
| [room_sensor]       | - | x | - | - | - | [BME280] | temperature, humidity, pressure, [motion], [illuminance], [miband], [miband_rssi] |
| [shelly_1_light]    | - | x | - | - | - | - | [light_switch]  |
| [shelly_1pm]        | - | - | - | [HLW8012] | - | - | current, power, [total_daily_energy] |
| [shelly_2_5_light]  | - | - | - | [ADE7953] | [NTC] | - | current, power, [total_daily_energy], [light_switch], device_temperature |
| [gosund_sp111]      | - | - | - | [HLW8012] | - | - | current, power, voltage, [total_daily_energy] |
| [ventilation]       | - | - | SI7021 | - |  - | - | temperature, humidity |

[DIY Hue]: https://diyhue.org/
[ESPHome]: https://esphome.io/
[ESPHome_logo]: https://esphome.io/_images/logo-text.svg
[Home Assistant]: https://www.home-assistant.io/
[Blitzwolf BW-RC1]: https://www.blitzwolf.com/BlitzWolf%C2%A0BW-RC1-WiFi-Smart-IR-Controller-with-360%C2%B0-Transmission,-APP-Control,-Works-with-Alexa,-Automatic-Identification,-DIY-Pairing-and-Slim-Design-p-409.html
[Gosund SP111]: https://www.gosund.com/download/smart_plug/126.html
[Koogeek KLOE4]: https://www.koogeek.com/p-kloe4.html
[Shelly 1]: https://shelly.cloud/products/shelly-1-smart-home-automation-relay/
[Shelly 1PM]: https://shelly.cloud/products/shelly-1pm-smart-home-automation-relay/
[Shelly 2.5]: https://shelly.cloud/products/shelly-25-smart-home-automation-relay/
[Sonoff Basic]: https://sonoff.tech/product/wifi-diy-smart-switches/basicr2
[Sonoff S20]: https://sonoff.tech/product/wifi-smart-plugs/s20
[Sonoff TH10]: https://sonoff.tech/product/wifi-diy-smart-switches/th10-th16
[Tuya QS-WiFi-D02-TRIAC]: https://expo.tuya.com/product/373634s
[Access Point Mode]: https://esphome.io/components/wifi.html#access-point-mode
[ADC]: https://esphome.io/components/sensor/adc.html
[ADE7953]: https://esphome.io/components/sensor/ade7953.html
[BME280]: https://esphome.io/components/sensor/bme280.html
[Binary]: https://esphome.io/components/light/binary.html
[Board]: https://esphome.io/components/status_led.html
[Captive Portal]: https://esphome.io/components/captive_portal.html
[DHT]: https://esphome.io/components/sensor/dht.html
[ESP32]: https://esphome.io/devices/esp32.html
[ESP8266]: https://esphome.io/devices/esp8266.html
[FastLED]: https://esphome.io/components/light/fastled.html
[GPIO]: https://esphome.io/components/binary_sensor/gpio.html
[HLW8012]: https://esphome.io/components/sensor/hlw8012.html
[Light]: https://esphome.io/components/light.html
[I²C]: https://esphome.io/components/i2c.html
[NTC]: https://esphome.io/components/sensor/ntc.html
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
[Xiaomi Miscale]: https://esphome.io/components/sensor/xiaomi_miscale.html
[bathroom_sensor]: https://github.com/ImEmJay/esphome-config/blob/master/bathroom_sensor_01.yaml
[blitzwolf_bw_rc1]: https://github.com/ImEmJay/esphome-config/blob/master/blitzwolf_bw_rc1_01.yaml
[diy_hue]: https://github.com/ImEmJay/esphome-config/blob/master/diy_hue_01.yaml
[gosund_sp111]: https://github.com/ImEmJay/esphome-config/blob/master/gosund_sp111_01.yaml
[koogeek_kloe4]: https://github.com/ImEmJay/esphome-config/blob/master/koogeek_kloe4_01.yaml
[illuminance]: https://github.com/ImEmJay/esphome-config/blob/master/common/sensor/illuminance.yaml
[ir_receiver]: https://github.com/ImEmJay/esphome-config/blob/master/common/remote_receiver/ir_receiver.yaml
[ir_transmitter]: https://github.com/ImEmJay/esphome-config/blob/master/common/remote_transmitter/ir_transmitter.yaml
[light_id]: https://github.com/ImEmJay/esphome-config/blob/master/common/text_sensor/light_id.yaml
[light_switch]: https://github.com/ImEmJay/esphome-config/blob/master/common/binary_sensor/light_switch.yaml
[miband]: https://github.com/ImEmJay/esphome-config/blob/master/common/binary_sensor/miband.yaml
[miband_rssi]: https://github.com/ImEmJay/esphome-config/blob/master/common/sensor/miband_rssi.yaml
[motion]: https://github.com/ImEmJay/esphome-config/blob/master/common/binary_sensor/motion.yaml
[room_sensor]: https://github.com/ImEmJay/esphome-config/blob/master/room_sensor_01.yaml
[shelly_1_light]: https://github.com/ImEmJay/esphome-config/blob/master/shelly_1_light_01.yaml
[shelly_1pm]: https://github.com/ImEmJay/esphome-config/blob/master/shelly_1pm_01.yaml
[shelly_2_5_light]: https://github.com/ImEmJay/esphome-config/blob/master/shelly_2_5_light_01.yaml
[sonoff_basic]: https://github.com/ImEmJay/esphome-config/blob/master/sonoff_basic_01.yaml
[sonoff_s20]: https://github.com/ImEmJay/esphome-config/blob/master/sonoff_s20_01.yaml
[gosund_sp111]: https://github.com/ImEmJay/esphome-config/blob/master/gosund_sp111_01.yaml
[total_daily_energy]: https://github.com/ImEmJay/esphome-config/blob/master/common/sensor/total_daily_energy.yaml
[tuya_qs_d02]: https://github.com/ImEmJay/esphome-config/blob/master/tuya_qs_d02_01.yaml
[ventilation]: https://github.com/ImEmJay/esphome-config/blob/master/ventilation.yaml
