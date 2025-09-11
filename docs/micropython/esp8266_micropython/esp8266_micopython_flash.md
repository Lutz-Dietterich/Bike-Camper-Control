


# ESP8266 mit MicroPython flashen

Diese Anleitung beschreibt, wie du den ESP8266 mit MicroPython flashen kannst.

## Voraussetzungen

- ESP8266
- USB-zu-Seriell-Adapter (z. B. FTDI oder CP2102)
- MicroPython Firmware für ESP8266 ([Download hier](https://micropython.org/download/esp8266/))
- `esptool.py` installiert:

  ```bash
  pip install esptool
  ```

## Schritt 1: MicroPython-Firmware herunterladen

1. Lade die neueste MicroPython-Firmware für den ESP8266 herunter (Dateiformat `.bin`). Du findest sie [hier](https://micropython.org/download/esp8266/).

2. Nach dem Herunterladen der `.bin`-Datei, wechsle in deinen Download-Ordner. Dies geht beispielsweise so:

   ```bash
   cd ~/Downloads
   ```

## Schritt 2: ESP8266 in den Flash-Modus bringen

1. Schließe den ESP8266 über das USB-zu-Seriell-Kabel an deinen Computer an.
2. Um den ESP8266 in den Flash-Modus zu versetzen:
   - Halte die `Flash`-Taste gedrückt (falls vorhanden).
   - Drücke die `Reset`-Taste und lasse sie los, während die `Flash`-Taste gedrückt bleibt.
   - Halte die `Flash`-Taste für ein paar Sekunden, bevor du sie loslässt.

Der ESP8266 befindet sich nun im Flash-Modus.

## Schritt 3: Firmware flashen

1. Lösche den Flash-Speicher des ESP8266 (optional, aber empfohlen):

   ```bash
   esptool.py --port /dev/cu.usbserial-110 erase_flash
   ```

2. Flash die MicroPython-Firmware auf den ESP8266:

   ```bash
   esptool.py --port /dev/cu.usbserial-110 --baud 115200 write_flash --flash_size=detect 0 ESP8266_GENERIC-20240602-v1.23.0.bin
   ```

   Achte darauf, den richtigen Port (`/dev/cu.usbserial-110`) und die Dateipfade zu verwenden.

## Schritt 4: Verbindung herstellen

Nach dem erfolgreichen Flashen kannst du über ein serielles Terminal (z. B. `screen`) mit dem ESP8266 kommunizieren:

```bash
screen /dev/cu.usbserial-110 115200
```

Wenn alles erfolgreich war, solltest du die MicroPython-REPL sehen:

```text
MicroPython v1.23.0 on 2024-06-02; ESP module with ESP8266
Type "help()" for more information.
>>>
```

## Schritt 5: Erste Schritte mit MicroPython

Hier ist ein einfaches Beispiel, um die eingebaute LED des ESP8266 blinken zu lassen:

```python
import machine
import time

led = machine.Pin(2, machine.Pin.OUT)  # Pin 2 ist normalerweise die eingebaute LED

while True:
    led.on()
    time.sleep(1)
    led.off()
    time.sleep(1)
```

## Hinweise

- Bei Verbindungsproblemen überprüfe den richtigen Port und die Verkabelung.
- Die Baudrate beim Flashen sollte auf 115200 eingestellt werden.

```

Diese Anleitung kannst du direkt in dein Obsidian-Wiki kopieren. Sie enthält alle Schritte und die notwendigen Befehle, um den ESP8266 mit MicroPython zu flashen.
