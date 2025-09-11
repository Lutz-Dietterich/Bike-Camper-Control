# Anleitung: ESP32 mit `esptool.py` flashen

Diese Anleitung zeigt Schritt für Schritt, wie du die Firmware auf deinen ESP32 flasht.

## Voraussetzungen

Bevor du mit dem Flashen beginnen kannst, stelle sicher, dass folgende Punkte erfüllt sind:

- **ESP32-Board**: Verbinde dein ESP32 über USB mit deinem Mac.
- **Firmware-Datei**: Du benötigst die entsprechende `.bin`-Firmware-Datei. Diese sollte im `Downloads`-Ordner gespeichert sein.
- **esptool.py**: Stelle sicher, dass das ESP-Tool installiert ist. Falls nicht, kannst du es über `pip` installieren:

    ```bash
    pip install esptool
    ```

## 1. Herausfinden, an welchem Port der ESP32 angeschlossen ist

Öffne das Terminal und gib den folgenden Befehl ein, um alle seriellen Ports aufzulisten:

```bash
ls /dev/cu.*
```

Dein ESP32 sollte als etwas wie `/dev/cu.usbserial-XXXX` angezeigt werden. Notiere dir den genauen Namen des Ports, in diesem Beispiel nehmen wir an, es ist `/dev/cu.usbserial-110`.

### 1.1. **Komplettes Löschen des Flash-Speichers:**

Um den Flash-Speicher komplett zu löschen, kannst du den folgenden Befehl in deinem Terminal ausführen:

```
esptool.py --chip esp32 --port /dev/cu.usbserial-110 erase_flash
```

Dadurch wird der gesamte Flash-Speicher des ESP32 gelöscht, einschließlich des Dateisystems und der gespeicherten Programme.
## 2. Terminal öffnen und in den Downloads-Ordner wechseln

Wenn deine Firmware-Datei sich im `Downloads`-Ordner befindet, kannst du mit diesem Befehl dorthin wechseln:

```bash
cd ~/Downloads
```

## 3. Flashen der Firmware

Verwende den folgenden Befehl, um die Firmware auf deinen ESP32 zu flashen:

```bash
esptool.py --chip esp32 --port /dev/cu.usbserial-110 --baud 460800 write_flash -z 0x1000 ESP32_GENERIC-20240602-v1.23.0.bin
```

### Erläuterung der Parameter:

- `--chip esp32`: Gibt an, dass du einen ESP32 verwendest.
- `--port /dev/cu.usbserial-110`: Der Port, an dem dein ESP32 angeschlossen ist.
- `--baud 460800`: Die Baudrate für den Flash-Vorgang (höhere Werte machen den Prozess schneller).
- `write_flash`: Befehl, um die Firmware zu schreiben.
- `-z 0x1000`: Gibt die Speicheradresse an, ab der die Firmware geschrieben wird (für ESP32 typischerweise 0x1000).
- `ESP32_GENERIC-20240602-v1.23.0.bin`: Der Name der Firmware-Datei, die geflasht wird.

## 4. Flash-Vorgang beobachten

Nachdem du den Befehl eingegeben hast, wird das Terminal den Flash-Vorgang starten und den Fortschritt anzeigen. Wichtige Schritte, die du sehen wirst:

- **Connecting...**: Verbindung zum ESP32 wird hergestellt.
- **Erasing Flash**: Der Flash-Speicher wird gelöscht (falls nötig).
- **Writing at 0x...**: Die Firmware wird geschrieben.
- **Hash of data verified**: Die Firmware wurde erfolgreich geschrieben.

Am Ende des Flash-Vorgangs wird eine Erfolgsmeldung wie "Hard resetting via RTS pin..." angezeigt.

## 5. Fehlerbehebung

Falls der Flash-Vorgang fehlschlägt, probiere die folgenden Lösungen:

- **Baudrate anpassen**: Verwende `115200` anstelle von `460800`, wenn Verbindungsprobleme auftreten.

    ```bash
    esptool.py --chip esp32 --port /dev/cu.usbserial-110 --baud 115200 write_flash -z 0x1000 ESP32_GENERIC-20240602-v1.23.0.bin
    ```

- **Reset-Taste**: Halte die `BOOT`-Taste auf dem ESP32 gedrückt, während du den Flash-Befehl ausführst.

## 6. Nach dem Flashen

Nach erfolgreichem Flashen wird der ESP32 automatisch neu gestartet. Du kannst nun mit der Nutzung deiner neuen Firmware beginnen.
