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
| [gosund_sp111]  | [Gosund SP111]  | Power Monitoring Plug |
| [koogeek_kloe4] | [Koogeek KLOE4] | Power Strip           |
| [sonoff_s20]    | [Sonoff S20]    | Power Plug            |

## Device specific firmware features

| Device  | [Platform]  | [Physical Button]  | [Status LED] | [Relay]
| --  |  :--: |  :--:  | :--:  |  :--: |
| [gosund_sp111]  | [ESP8266] | x  | x |  x |
| [koogeek_kloe4] | [ESP8266] | x  | x |  x |
| [sonoff_s20]    | [ESP8266] | x  | x |  x |

## Device specific sensors

| Device  | [HLW8012] | Features
| --  |  :--: | --  |
| [gosund_sp111]  | x | current, power, voltage, [total_daily_energy] |
| [sonoff_s20]    | - ||                                               |

[ESPHome]: https://esphome.io/
[ESPHome_logo]: https://esphome.io/_images/logo-text.svg
[Home Assistant]: https://www.home-assistant.io/
[Gosund SP111]: https://www.gosund.com/download/smart_plug/126.html
[Koogeek KLOE4]: https://www.koogeek.com/p-kloe4.html
[Sonoff S20]: https://sonoff.tech/product/wifi-smart-plugs/s20
[Access Point Mode]: https://esphome.io/components/wifi.html#access-point-mode
[Board]: https://esphome.io/components/status_led.html
[Captive Portal]: https://esphome.io/components/captive_portal.html
[ESP8266]: https://esphome.io/devices/esp8266.html
[HLW8012]: https://esphome.io/components/sensor/hlw8012.html
[Native API]: https://esphome.io/components/api.html
[Over The Air]: https://esphome.io/components/ota.html
[Physical Button]: https://esphome.io/components/binary_sensor/gpio.html
[Platform]: https://esphome.io/components/status_led.html
[Relay]: https://esphome.io/cookbook/relay.html
[Restart Switch]: https://esphome.io/components/switch/restart.html
[Status Binary Sensor]: https://esphome.io/components/binary_sensor/status.html
[Status LED]: https://esphome.io/components/status_led.html
[Time]: https://esphome.io/components/time.html
[Uptime Sensor]: https://esphome.io/components/sensor/uptime.html
[Web Server]: https://esphome.io/components/web_server.html
[Wifi]: https://esphome.io/components/wifi.html
[Wifi Signal Sensor]: https://esphome.io/components/sensor/wifi_signal.html
[gosund_sp111]: https://github.com/ImEmJay/esphome-config/blob/master/gosund_sp111_01.yml
[koogeek_kloe4]: ttps://github.com/ImEmJay/esphome-config/blob/master/koogeek_kloe4_01.yml
[sonoff_s20]: https://github.com/ImEmJay/esphome-config/blob/master/sonoff_s20_01.yml
[gosund_sp111]: https://github.com/ImEmJay/esphome-config/blob/master/gosund_sp111_01.yml
[total_daily_energy]: https://github.com/ImEmJay/esphome-config/blob/master/common/sensor/total_daily_energy.yaml
