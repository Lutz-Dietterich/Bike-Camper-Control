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
Der Fahrradwohnwagen wurde von Grund auf als ein mehrschichtiger Verbundwerkstoff-Körper in GFK-Leichtbauweise konzipiert. Dieses Composite-Verfahren ermöglicht eine extrem hohe strukturelle Stabilität bei minimalem Gewicht, was für einen Fahrradwohnwagen entscheidend ist.

Die gesamte Konstruktion und Fertigung wurden vollständig eigenständig in eigener Werkstatt realisiert. Alle CNC-Präzisionsteile und komplexen Formteile wurden mit eigenen Maschinen gefräst beziehungsweise mit 3D-Druck-Technologie gefertigt. Diese Autarkie im Fertigungsprozess gewährleistete eine durchgängige Kontrolle über die Qualität und ermöglichte eine präzise Umsetzung des Designs von der ersten Idee bis zum fertigen Produkt.

Eine integrierte Wärmedämmung macht den Wohnwagen zudem für verschiedene klimatische Bedingungen nutzbar und unterstreicht den hohen Anspruch an Funktionalität und Komfort.

## Solar System

<table>
  <tr>
    <td><img src="docs/Camper/camper_images/20250328_100722.jpg" alt="Solar Panel Installation"></td>
    <td><img src="docs/Camper/camper_images/20250328_100911.jpg" alt="Solar System Components"></td>
    <td><img src="docs/Camper/camper_images/20250818_202525.jpg" alt="Solar Panel Detail"></td>
  </tr>
</table>

## Licht Konzept

<table>
  <tr>
    <td><img src="docs/Camper/camper_images/20250508_195653.jpg" alt="LED Beleuchtung Konzept"></td>
    <td><img src="docs/Camper/camper_images/20250508_200309.jpg" alt="Lichtinstallation Detail"></td>
    <td><img src="docs/Camper/camper_images/20250508_215501.jpg" alt="Beleuchtung bei Nacht"></td>
  </tr>
</table>

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
