# myesphomes

My esphome projects

## Goals

Deploy wifi connected sensors in my home

- Cheap
- Resilient (manage re-connections)
- Connectable to Openhab (my domotic system)

## References

- https://esphome.io/

## Preparation

See <https://esphome.io/guides/installing_esphome>

- Install python
- Create virtual env

```bash
python3 -m venv .venv
```

- Activate virtual env

```bash
source .venv/bin/activate
```

- Instalar esphome (y requisitos)

```bash
pip install -r requirements.txt
```

## PROJECT: Presence sensors 

### References

See <https://smarthomescene.com/diy/diy-presence-sensor-with-hi-link-ld2410-and-esp32-for-home-assistant/>

### Hardware

- Presence sensor: LD2410c
- Microcontroller: ESP32 WROOM 32U

### Configuration

See [config file](presence.yaml)

### Install

- Connect esp32 to PC vía USB to a good USB (enough current, avoid old usb 2 ports)
- Activate virtual env
- Review and adapt configuration, if needed 
    - Configure secrets (for example: wifi)
- Flash esp32 (maybe several attempts needed)

```bash
esphome run presence.yaml
```

- When all done, disconnect from PC
- Connect LD2410. Use GPIO 16, 17 for tx and rx (see presence.yaml)

| ESP32 Board	| HLK-LD2410 |
| 5V	        | VCC |
| GND	        | GND |
| RX (eg. GPIO17)	| TX |
| TX (eg. GPIO16)	| RX |

- Connect to current USB (not needed PC from this point)

### Check and configure

In yaml is activated web server

- Guess device IP
- Connect to http://IP-OF-ESP32:8082

### Openhab


