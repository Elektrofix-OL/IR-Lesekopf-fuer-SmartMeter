# IR Lesekopf für SmartMeter
kompakter DO-Leser über WLAN mit Wemos-D1-mini

Im Januar'21 wollte ich einen SmartMeter auslesen, jedoch ohne Eingriff in die Verteilung, daher entschied ich mich die IR-Diode und Fototransisor direkt an die Wemos anzuschließen und alles in einem Gehäuse unterzubringen.

# Die Schaltung
![](https://github.com/Elektrofix-OL/IR-Lesekopf-fuer-SmartMeter-/blob/main/Eagle/sch.gif)
Im Grunde ist es ganz einfach, Der Fototransitor (SFH 229) wird zwischen RX und GND angeschlossen und bekommt einen Pull-Up Widerstand von 1200 Ohm nach 3,3V. Die IR-LED mit 880nm Wellelänge wird mit Vorwiderstand 180 Ohm direkt zwischen 3,3V und TX angeschlossen.
Der Kondensator 10uF wird zwischen 3.3V und GND geschaltet und dient nur der Stüzung der Versorgungsspannung, wenn Daten übertragen werden.

# Gehäuse-Bilder
![](https://github.com/Elektrofix-OL/IR-Lesekopf-fuer-SmartMeter-/blob/main/Fotos/Back.JPG)
Ich hatte noch ein kleines Display herumliegen und habe es dazu genutz, das diese mir die IP-Adresse anzeigt, so das ich den Leser auch im Netz ansprechen kann.
Die Dateien für einen 3D-Drucker findet ihr unter https://www.thingiverse.com/thing:5175959
# Software
Die Herausforderung war, eine Übertragung über das Internet über eine Freifunkverbindung zu realisieren. Mit espEasy geht es nur im gleichen netztwerk, daher habe ich mich für Tasmota-SML entschieden.

Leider Kann ich Euch die Datei nicht zur Verfügung stellen, da dort meine Daten fest hinterlegt sind. Einen Anleitung zum Erstellen der Software hat Mattihas Kleine erstellt https://www.youtube.com/watch?v=s6qQs4FN9B0

Ihr findet hier eine Textdatei mit dem Skript für Tasmota. Es bewirkt nicht nur das Auslesen, sondert gibt auch in den ersten 30 Sec. auf dem Display die IP-Adresse, SSID und RSSI aus. Die Tasmota-SML-Display.bin ist eine Datei zum Flashen auf den ESP8266. 

# Lizenz
Copyright (c) 2021 Elektrofix

Jeder Mensch darf das Projekt benutzen, kopieren und verändern. Der Verkauf ist jedoch verboten und auch nach der Veränderung dürfen Teile des Projekten nicht veräußert werden. Ihr habt es kostenlos bekommt, also müsst ihr die Änderungen auch Kostenlos weitergeben! Geld machen mit meinen Ideen ist nicht!

Der obige Urheberrechtshinweis und dieser Genehmigungshinweis müssen in alle Kopien oder wesentlichen Teile der Software aufgenommen werden.

Alles macht ihr auf eigenes Risiko, Haftung und Gewährleistung über nehme ich keine.
