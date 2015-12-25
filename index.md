---
layout: default
title: Sensor Parts Zusammenarbeit
---

## SensorAPI
- empfängt Daten von physischen Sensor via WLAN
- Spec & Test: https://github.com/CodeforChemnitz/SensorAPI/blob/master/doc/APIv1.md

    http://localhost:5000/

Notwendige Header:
- `X-Sensor-Version: 1`

**URIs:**
- `/users`
- `/users/<int:id>/<approval_code>`
- `/sensors`
- `/sensors/<int:sensor_id>`

## SensorSimulator / Sensor
- simuliert einen physischen Sensor
- wird von Provisionierer konfiguriert
- sendet Daten an SensorAPI
- Spec & Test: https://git.dinotools.org/poc/SensorNodeESP8266/about/

    http://localhost:5001

**URIs:**
- [x] `/action/register` POST `name`, `email` - Nutzer registrieren
- [X] `/action/restart` - Sensor neustarten
- [X] `/action/save` - Konfiguration in EEPROM speichern
- [X] `/config/api/hostname?hostname=<api_hostname>` - Hostname/Domain der Sensor-API (localhost)
- [X] `/config/api/port?port=<api_port>` - Port der Sensor-API (5000)
- [X] `/config/wifi/sta/ssid?ssid=<ssid>` -
- [X] `/config/wifi/sta/password?password=<password>` -
- [x] `/info/wifi/ssids` - sichtbare SSIDs zeigen (JSON)
- [ ] `/info/wifi/sta` - Liste mit STA (JSON)
- `/setup` - Mini-GUI
- [ ] `/config/sensor/<int:sensor_id>` - einzelne Sensoren anlegen/konfigurieren

## SensorProvisioning
- ist eine NW.js App
- konfiguriert einen physischen Sensor oder den SensorSimulator
- kommuniziert NICHT zur SensorAPI
