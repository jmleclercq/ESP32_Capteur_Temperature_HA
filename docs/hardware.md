# Hardware

## Supported boards
This project targets common **ESP32 dev boards** (e.g. ESP32 DevKit / ESP32-WROOM).

## Sensor
- **DHT22 / AM2302** temperature & humidity sensor

## Power
- Use **3.3V** (recommended).
  Some DHT22 modules accept 5V, but **data level** must stay compatible with the ESP32.

## Wiring diagram
See `docs/images/wiring.png`.

## Notes / gotchas
- Many DHT22 breakout boards already include a pull-up resistor on DATA.
- If you use a bare DHT22, add a **10kΩ pull-up** from **VCC** to **DATA**.
