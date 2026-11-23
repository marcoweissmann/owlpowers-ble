# OwlPowers BLE

Kleine Web-App, die den Status einer Powerstation per Web Bluetooth ausliest und anzeigt:
Akkustand, Ein- und Ausgangsleistung, Restlaufzeit, AC/DC/Licht. Die Ausgänge lassen sich auch schalten.

Getestet mit der ALLPOWERS S300 V2. Inoffizielles Hobbyprojekt, nicht mit ALLPOWERS verbunden
oder von ALLPOWERS unterstützt.

## Nutzung

Web Bluetooth funktioniert nur in Chrome oder Edge (Desktop und Android) über `https://` oder
`http://localhost`. Safari, iOS und Firefox werden nicht unterstützt.

Lokal starten:

```bash
python3 -m http.server 8080
```

Dann `http://localhost:8080` öffnen und auf **Verbinden** klicken.

## Protokoll

Nach den Open-Source-Projekten
[madninjaskillz/allpowers-ble](https://github.com/madninjaskillz/allpowers-ble) und
[dedalodaelus/esphome-allpowers-ble](https://github.com/dedalodaelus/esphome-allpowers-ble):
Service `FFF0`, Notify `FFF1`, Write `FFF2`, Pakete beginnen mit `A5 65` und enden mit einer XOR-Prüfsumme.
Beide Lampen teilen sich ein Statusbit (`0x10`) und lassen sich nicht einzeln schalten.
