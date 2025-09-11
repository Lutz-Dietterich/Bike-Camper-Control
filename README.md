# Smart-Home System für Fahrradwohnwagen

## Projektübersicht

Das Smart-Home System-Projekt ermöglicht die Entwicklung eines eigenen Smart-Home Systems basierend auf einem Raspberry Pi Zero W2 als zentrale Steuereinheit und ESP32/ESP8266-Modulen als dezentrale Sensorknoten. Das System bietet umfassende Überwachung und Steuerung verschiedener Komponenten für optimalen Komfort und Energieeffizienz.

## Hardware-Komponenten

### Zentrale Steuereinheit

-   **Raspberry Pi Zero W2**: Hauptcontroller mit MQTT-Broker und Web-Server

### Mikrocontroller-Module

-   **ESP32**: Für komplexere Steuerungsaufgaben (Lichtsteuerung, mehrere Sensoren)
-   **ESP8266**: Für einfache Sensoraufgaben (Temperatur, Luftqualität)

### Sensoren

-   **BME280**: Temperatur, Luftfeuchtigkeit und Luftdruck
-   **SCD40**: CO2-Sensor für Luftqualitätsmessung

### Aktoren

-   **WS2812 LEDs**: Adressierbare RGB-LED-Streifen für Beleuchtung
-   **Noctua 5V PWM Lüfter**: Leise und effiziente Lüftungssteuerung

## APP Design

<table>
  <tr>
    <td><img src="docs/design/FaWoWa-Control-Home.png" alt="Home Control Interface"></td>
    <td><img src="docs/design/FaWoWa-Control-Settings_Temperature.png" alt="Temperature Settings"></td>
    <td><img src="docs/design/FaWoWa-Control-Lights.png" alt="Light Control Interface"></td>
  </tr>
</table>

### Web App

-   **Repository**: https://github.com/Lutz-Dietterich/fawowa-next-app
-   **Demo**: https://fawowa-next-app.vercel.app/

## Fahrradwohnwagen

<table>
  <tr>
    <td><img src="docs/Camper/camper_images/20250419_201529.jpg" alt="Fahrradwohnwagen Außenansicht"></td>
    <td><img src="docs/Camper/camper_images/20250404_074943.jpg" alt="Innenbereich des Wohnwagens"></td>
    <td><img src="docs/Camper/camper_images/20250818_200319.jpg" alt="Wohnwagen Setup"></td>
  </tr>
</table>

### Konstruktion und Fertigung

Der Fahrradwohnwagen wurde als mehrschichtiger Verbundwerkstoff-Körper in GFK-Leichtbauweise entworfen. Dieses Composite-Verfahren ermöglicht eine extrem hohe Stabilität bei minimalem Gewicht, was für einen Fahrradwohnwagen entscheidend ist.

Die gesamte Konstruktion und Fertigung wurden vollständig eigenständig in eigener Werkstatt realisiert. Alle Komponenten, einschließlich der CNC-Präzisionsteile und komplexen Formteile, wurden selbst in CAD-Software designt und anschließend mit eigenen Maschinen gefräst beziehungsweise mit 3D-Druck-Technologie gefertigt. Diese Autarkie im Design- und Fertigungsprozess gewährleistete eine durchgängige Qualitätskontrolle und eine präzise Umsetzung des Konzepts von der ersten Idee bis zum fertigen Produkt.

Eine integrierte Wärmedämmung macht den Wohnwagen zudem für verschiedene klimatische Bedingungen nutzbar und unterstreicht den hohen Anspruch an Funktionalität und Komfort.

## Solar System

<table>
  <tr>
    <td><img src="docs/Camper/camper_images/20250328_100722.jpg" alt="Solar Panel Installation"></td>
    <td><img src="docs/Camper/camper_images/20250328_100911.jpg" alt="Solar System Components"></td>
    <td><img src="docs/Camper/camper_images/20250818_202525.jpg" alt="Solar Panel Detail"></td>
  </tr>
</table>

### Solar- und Energiesystem

Der Fahrradwohnwagen ist mit einem autarken 12V-Solarsystem mit einer Spitzenleistung von 150W ausgestattet. Dieses System ist darauf ausgelegt, auch bei minimaler Sonneneinstrahlung die grundlegenden Energiebedürfnisse zu decken. Mit den 150W Peak-Panels ist eine autarke Versorgung für gängige Verbraucher wie Smartphones, Internet-Hotspots und die Bordelektronik gewährleistet, sodass der Betrieb über rund 10 Tage ohne direkte Sonne sichergestellt ist.

### Vielseitigkeit, Effizienz und Überwachung

Die modulare Bauweise der Solarpaneele ermöglicht eine flexible Nutzung. Sie können so positioniert werden, dass sie auch bei einem im Schatten abgestellten Wagen immer perfekt zur Sonne ausgerichtet sind. Im Sommer wird stets genügend Energie erzeugt, um die Bordelektronik, das IT-System samt Server und Microcontroller sowie alle persönlichen Geräte zu versorgen.

Ein integriertes selbstentwickeltes Powerstation-System sorgt für maximale Zuverlässigkeit. Die modulare Bauweise der Powerstation schafft eine eingebaute Redundanz: Sollte ein Teil der Batterie ausfallen, bleibt das Gesamtsystem weiterhin voll funktionsfähig. Ein integriertes Batteriemanagementsystem (BMS) optimiert nicht nur die Lade- und Entladevorgänge des Akkus, sondern schützt ihn auch vor Überladung und Tiefentladung. Die Solaranlage ist zusätzlich mit einem Tracking-System ausgestattet, das eine detaillierte Überwachung der Solarleistung in Echtzeit ermöglicht. Dies sorgt für maximalen Überblick über den Energiefluss und die Effizienz des Systems. Darüber hinaus kann bei sonnigen Verhältnissen auch der Fahrradakku problemlos geladen werden. Diese hohe Effizienz stellt eine 100%ige Unabhängigkeit von externen Stromquellen sicher und unterstreicht die autarke Natur des Projekts.

## Licht Konzept

<table>
  <tr>
    <td><img src="docs/Camper/camper_images/20250508_195653.jpg" alt="LED Beleuchtung Konzept"></td>
    <td><img src="docs/Camper/camper_images/20250508_200309.jpg" alt="Lichtinstallation Detail"></td>
    <td><img src="docs/Camper/camper_images/20250508_215501.jpg" alt="Beleuchtung bei Nacht"></td>
  </tr>
</table>

### Beleuchtung und Lichtsteuerung

Das Beleuchtungssystem des Wohnwagens ist in drei individuelle Zonen aufgeteilt. Jede Zone wird mit adressierbaren LEDs realisiert, was eine präzise und flexible Lichtgestaltung ermöglicht.

Die Steuerung erfolgt primär über eine Tasmota-Schnittstelle und ein eigenes Web-Interface, das über einfache HTTP-Requests bedient wird. Diese Art der Steuerung gewährleistet maximale Kompatibilität mit verschiedenen Geräten und Systemen.

Für den Fall eines Totalausfalls des IT-Systems oder des Web-Interfaces ist die Funktionsfähigkeit der Beleuchtung durch eine redundante Steuerung gesichert: Analoge Schalter ermöglichen weiterhin die grundlegende Bedienung der Lichtanlage.

Für eine optimale Anpassung an jede Situation kann die Beleuchtung bei Bedarf sehr hell eingestellt werden. Gleichzeitig bietet das System auch eine rote Ambientebeleuchtung für die Nacht. Rotlicht hat nicht nur den entscheidenden Vorteil, dass es die natürliche Dunkeladaption des menschlichen Auges nicht beeinträchtigt, sondern bietet auch einen taktischen Nutzen: Die rote Beleuchtung ist aus der Ferne deutlich schwerer zu erkennen als weißes Licht, was die Sichtbarkeit des Wohnwagens bei Dunkelheit reduziert. Dies kann die Sicherheit erhöhen und ist besonders in der Wildnis von Vorteil. Die Sehkraft im Dunkeln bleibt erhalten, was nachts oder in der Dämmerung nützlich ist, um sich im Wohnwagen zu orientieren, ohne geblendet zu werden.

### Licht Steuerung

-   **Repository**: https://github.com/Lutz-Dietterich/led-website
-   **Technologie**: WS2812 adressierbare LED-Streifen
-   **Features**: Farb- und Helligkeitssteuerung, Effekte und Szenen

## Kontrollierte Wohnraumlüftung

### Funktionen

-   Kontinuierliche Messung der Luftqualität mit SCD40 (CO2) und BME280 (Temperatur, Luftfeuchtigkeit)
-   Automatische Steuerung der Noctua 5V PWM Lüfter basierend auf Messwerten
-   Energieeffiziente PWM-Regelung für optimale Lüftergeschwindigkeit

### Repositories

-   **Lüftersteuerung**: https://github.com/Lutz-Dietterich/FaWoWa_Fan
-   **Temperatur-/Luftfeuchtigkeitssensor**: https://github.com/Lutz-Dietterich/FaWoWa_Temp_Bme280

## ESP-Konfiguration

### Access Point Interface für WLAN-Konfiguration

-   **Repository**: https://github.com/Lutz-Dietterich/micropython_esp32-template
-   **Features**: MicroWebSrv mit Access Point für einfache WLAN-Konfiguration der ESP-Module
-   **Unterstützte Module**: ESP32 und ESP8266

## System-Funktionalitäten

### Umweltüberwachung

-   **Temperatur und Luftfeuchtigkeit**: BME280-Sensoren in verschiedenen Bereichen
-   **Luftqualität**: SCD40-Sensoren für CO2-Überwachung
-   **Luftdruck**: Zusätzliche Wetterinformationen über BME280

### Automatisierte Steuerung

-   **Intelligente Lüftung**: Automatische Anpassung der Noctua PWM-Lüfter basierend auf CO2-Werten
-   **Adaptive Beleuchtung**: WS2812 LED-Steuerung mit Szenen und Zeitplänen
-   **Energiemanagement**: Integration mit Solarsystem für optimierte Energienutzung

### Benutzeroberfläche

-   **Web-Dashboard**: Responsive Next.js-Anwendung
-   **Mobile Unterstützung**: Optimiert für Smartphone und Tablet
-   **Echtzeit-Updates**: MQTT-basierte Live-Datenübertragung

## Technische Architektur

### Kommunikation

-   **Protokoll**: MQTT für alle Geräte-zu-Gerät Kommunikation
-   **Broker**: Mosquitto auf Raspberry Pi Zero W2
-   **Netzwerk**: WLAN mit automatischer ESP-Konfiguration

### Software-Stack

-   **Zentrale**: Python mit MQTT-Client auf Raspberry Pi Zero W2
-   **ESPs**: MicroPython für ESP32/ESP8266
-   **Frontend**: Next.js Web-Anwendung
-   **Backend**: Node.js mit MQTT-Integration

## Implementierungsschritte

### 1. Hardware-Setup

-   Raspberry Pi Zero W2 Einrichtung mit Raspbian OS
-   MQTT-Broker (Mosquitto) Installation und Konfiguration
-   ESP32/ESP8266 Module mit Sensoren und Aktoren verbinden

### 2. Software-Entwicklung

-   MicroPython-Firmware auf ESP-Module flashen
-   MQTT-Kommunikation zwischen allen Komponenten etablieren
-   Web-Server und Dashboard auf Pi Zero W2 implementieren

### 3. Sensor-Integration

-   BME280-Sensoren für Umweltdaten kalibrieren
-   SCD40-Sensoren für CO2-Messung einrichten
-   Datenerfassung und -übertragung optimieren

### 4. Aktor-Steuerung

-   WS2812 LED-Streifen programmieren und testen
-   Noctua PWM-Lüfter Steuerung implementieren
-   Automatisierungslogik entwickeln

### 5. System-Integration

-   Alle Komponenten in das MQTT-Netzwerk integrieren
-   Web-Interface finalisieren und testen
-   Monitoring und Logging implementieren
