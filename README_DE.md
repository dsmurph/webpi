

<p align="center"><img src="resources/webpi.png" alt="WebPi Logo" width="100"></p>

<h3 align="center">Das Hardware und Software-Logik Framework</h3>


---


**[Read this in English 🇺🇸](README.md)**


**🚀 WebPi die Brücke zwischen modernem Linux und deinen Hardware-Projekten.**

WebPi ist ein leichtgewichtiges C++ Webinterface-Framework für den Raspberry Pi. Es wurde entwickelt, um Sensoren, Aktoren und Gerätezustände über eine einfache HTTP-API und eine saubere, moderne Weboberfläche steuerbar zu machen – ohne den Ballast schwerfälliger externer Frameworks.

**"Offen, ehrlich und transparent."**

WebPi ist nicht nur ein Werkzeug; es ist eine Einladung, die Welt von C++ und der hardwarenahen Programmierung zu entdecken.

---

## ⚛️ Die Philosophie
WebPi entstand aus der Erfahrung, dass die Entwicklung auf dem Raspberry Pi immer komplexer und schwieriger wird. Zwischen Kernel-Updates (Debian 13 Trixie) und Hardware-Wechseln (Pi 5) geht das einfache "GPIO-Gefühl" oft verloren.

WebPi bringt dieses Gefühl zurück. Es verpackt komplexe Mechanismen in klare, lesbare Schnittstellen. Es versteckt nicht, wie die Dinge funktionieren – es erklärt sie und macht C++ für jeden zugänglich.

---

## ✨ Highlights

* **🌐 Autarkes Ökosystem:** Integrierter HTTP-Server und modulares Core-System. Kein externer Webserver wie Apache oder Nginx erforderlich.
* **🔢 Bitmasken-Logik:**    Effizient, vorhersehbar und einfach zu visualisieren. Die Handhabung von 8-Bit- oder 16-Bit-Zuständen bleibt im gesamten System konsistent.
* **🛠 Modulare Power:**     Nutze nur, was du brauchst. Das Benutzerfreudliche WebPiEasy, mit vielen vereinfachten Wrapper Funktionen. Von Hardware-Modulen Expander, Funkmodulen und Entfernungsmesser bis zu einfach verständlichen Board-Treibern wie SPI, I2C und UART.
* **🔌 GPIO-Steuerung:**     WebPi bringt seine eigene einfachgehaltene GPIO-Lib mit. Konfigurieren Output/Input, Schreiben/Lesen setPin/getPin und eine kleine Interrupt-Funktion ist auch dabei.
* **📖 Dein Fortschritt**    Viele WebPi-Funktionen bedienen dich per Default-Parameter und können mit eigenen Werten angepasst werden.
* **🛟 WebPi-Start:**        Ein Bash-basiertes Kontrollzentrum, das Abhängigkeiten, Builds auf Knopfdruck verwaltet. Für den einfachen Start, baut es euch die Kontroll und Lernplattform WebPiUI mit der ihr dann voll einsteigen könnt. Examples bauen und Code mit der visuellen Weboberfläche vergleichen, was funktioniert wie und warum.
* **⚠️ WebPi-Apps:**         Apps aus System und eigenen Bibliotheken, zum sofort loslegen. Passe dir die Applikationen an deine Bedürfnisse an und mache sie zu deinem Projekt.

---

## 🧱 Architektur im Überblick
WebPi ist modular und übersichtlich strukturiert.
Die Erweiterungen sind nicht miteinander verknüpft und können so auch für eigene Zwecke verwendet werden.


```text
WebPi/
├─ core/            # Das Herzstück (API, Bitmasken, Server)
├─ apps/            # Zentrales Verzeichnis für WebPi Applikationen zum benutzen, erweitern und anpassen.
├─ docs/            # Erste Schritte im Umgang mit WebPi, erweiterte Funktionsbeschreibungen und Informationen rund um dieses Projekt.
├─ extensions/      # Erweiterungen die dir den Einstieg und das "Leben" leichter machen.
│  ├─ webpidevices/    # Gängige und Beliebte Hardware-Module werden unterstützt und im laufe der Zeit erweitert.
│  ├─ webpimodules/    # Boardmittel mit einfachen und verständlichen Schnittstellen.
|  ├─ webpidrivers/    # Basis Treiber für die GPIO Controller und Pin Steuerung. 
│  └─ webpieasy/       # WebPiEasy ist eine Wrapper-Zusammenstellung die dir den Einstieg erleichtern. Einfachgehaltene Funktionen, kurze Bezeichnungen zum merken und der interne C++ Kern wird nicht versteckt.
├─ examples/        # Von "Hello WebPi" das Grundgerüst von WebPi, bis hin zu SVG-Temperaturgraphen und BitMasken Umgang zum Anfassen.
└─ webpiStart       # Das Schweizer Taschenmesser für den ersten Schritt mit WebPi.

```
---

## 🔢 Das Bitmasken-Konzept zum Anfassen
WebPi macht binäre Logik sichtbar. Das Example `actuators` zeigt direkt, wie die interne 8-Bit Maske mit der Weboberfläche korrespondiert.

![WebPi Actuators](resources/actuators.jpg)
*Klarheit durch Visualisierung: Bitmasken-Zustände in Echtzeit.*

---

## 📈 Bereit für echte Daten
Egal ob Temperaturverläufe oder System-Logs – WebPi bietet bereits im Kern die Werkzeuge, um Daten nicht nur zu verarbeiten, sondern auch ansprechend zu präsentieren.

![WebPi Temperature Graph](resources/tempsensor.jpg)
*Beispiel einer Sensor-Integration mit SVG-Charts und Logbuch-Funktion.*

---

## 🛠️ WebPi Status 
WebPi befindet sich in einem fortgeschrittenen Stadium kurz vor der Veröffentlichung.
Du kannst die Entwicklung anhand der Source-List mitverfolgen.


Stay tuned! 
