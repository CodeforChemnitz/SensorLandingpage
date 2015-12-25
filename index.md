---
layout: default
title: Zusammenarbeit der Projekt-Teile
---

Die einzelnen Teile des Projektes arbeiten wie folgt zusammen.

<div class="mermaid">
graph TB
  subgraph Erfassung
    Umweltdaten-->Sensor
    Sensor-->API
    API-->Datenbank
  end
  subgraph Auswertung
    Karte-->Datenbank
  end

  subgraph Setup
    Provisionierung-->Sensor
    Provisionierung-->Simulator
  end
</div>

**Projekte auf GitHub:**

- [Sensor-API](http://github.com/codeforChemnitz/SensorAPI)
- [Sensor-Provisionierung](http://github.com/codeforChemnitz/SensorProvisioning)
- [Sensor-Karte](http://github.com/codeforChemnitz/SensorKarte)
- [Sensor-Simulator](http://github.com/codeforChemnitz/SensorSimulator)  -> [codefor-sensors.meteor.com](http://codefor-sensors.meteor.com/)

## Einrichtung des Sensors

Die Erstkonfiguration des Sensors kann bequem über das [Provisionierungs-Tool](http://github.com/codeforChemnitz/SensorProvisioning) erfolgen.
Nach dem Download des Tools wird der Sensor im Setup-Modus angeschalten. Er eröffnet dabei sein eigenes WLAN.
Das Provisionierungs-Tool verbindet sich mit diesem und stellt dann eine Oberfläche zur einfachen Konfiguration bereit.

## Erfassung von Daten

Ein fertig konfigurierter Sensor kann im Betriebsmodus an einer geeigneten Stelle platziert werden.
Er muss Zugriff zum konfigurierten WLAN haben (z.B. Freifunk) um die Daten zyklisch zur [Sensor-API](http://github.com/codeforChemnitz/SensorAPI) zu senden.
Diese speichert sie in seiner Datenbank.

## Auswertung der Daten

Von der Sensor-API können über deren REST-Schnittstelle diese Daten wieder abgefragt werden. Der Zugriff steht per Auth-Token allen offen.
Eine Beispiel-Anwendung ist die [Sensor-Karte](https://github.com/CodeforChemnitz/SensorKarte). In dieser sind alle registrierten Sensoren und deren Standorte aufgeführt. Künftig sollen dort die jeweils erfassten Daten auch eingesehen werden können.

Zum Beipiel könnten die Sensor-Daten auch mit [Graphana](http://grafana.org) aufbereitet werden.

## [Weitere Details](details.html)
