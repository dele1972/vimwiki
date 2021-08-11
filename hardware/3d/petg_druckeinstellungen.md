PETG Einstellungen


## Quellen

- **Phillips 3D Druck**: [PETG DRUCKEN - Slicin Einstellungen + Heat Tower [Tutorial]](https://youtu.be/wlRO5C9CUb0)
- **Thomas Sanladerer**: [Things you should know about PETG](https://youtu.be/8_adY2K-YIc)


## benutztes Filament

### YouTube

- material4print
- Artikel-Nr. 20600511141
- Extr.Temp.: 210 - 240°C
- Plate Temp.: 60-80°C


### Meins

- Sunlu 
- Extr.Temp.: 220 - 250°C
- Plate Temp.: 70-80°C


## Tipp vorab

- Buildtak als Unterlage
  - Thomas sagt auch, besser nicht direkt auf Glas drucken - er empfiehlt Druckplattenkleber - adhesion
- Abstand sollte 1/10 zum Druckkopf betragen
- zuerst einen Heat Tower für jede Rolle Filament ausdrucken
- [Thomas](https://youtu.be/8_adY2K-YIc?t=256) sagt:
  - falls das PETG Filament zu feucht ist, kann man das auch in den Ofen packen
    - feuchtes Filament ist brüchiger
    - Dauer: 1-2 Stunden
    - Temp.: 60°C
  - Nachbearbeitung auch mit Heißluftpistole möglich um Strings wegzuschmelzen

## Warum

- Hitzebeständiger als PLA (dort 60°)
  - Geschirrspülmaschinen geeignet
  - im Auto einsetzbar (Hitze im Sommer resistent)
- 'geruchlos' wie PLA
- höhere Stabilität, flexibler, schlagfester
- kein warping
- relativ günstig


## Nachteile

- aber etwas schwerer als PLA druckbar
- Tendenz zum Thrinning / Fadenbildung
- Skulpturen besser PLA verwenden
- nicht klebbar (nur sehr schwierig)
- nicht/schwer bemalbar


## Cura Einstellungen

Am Besten neben den Profil Filter auf das Hamburger-Menu klicken und *advanced* auswählen.


### Qualität

[Qualität](https://youtu.be/wlRO5C9CUb0?t=585)

- **Schichtdicke**: 0.15 mm
  - guter Kompromiss zwischen 0.1 und 0.2 zu Geschwindigkeit/Qualität
- **Dicke der ersten Schicht**: 0.3
   - immer etwas dicker Wählen als die normale Schichtdicke um die Druckbetthaftung zu erhöhen
- **Linienbreite**: 0.4 mm (sollte immer durch Düsenbreite restlos teilbar sein)
- **Linienbreite der ersten Schicht**: 130%
  - das gleicht unebenheiten im 'buildtag'(?)
  - das PETG kann sich gut in die **rauhe** Oberfläche reindrücken -> sehr sehr gute Druckbetthaftung vom Bauteil


## Gehäuse

[Gehäuse](https://youtu.be/wlRO5C9CUb0?t=653)

*kann man je nach Bauteil einstellen was man will*

- **Anzahl der Wandlinien**: 4
  - variiert zwischen 2 und 4, je nachdem wie stabil das Teil werden soll
- **Obere/ Untere Dicke**: 1 mm
  - kann auch auf 0.5 oder weniger gesetzt werden (bei schönen Teilen)?
- **Obere/ Untere Schichten**: 7mm
- **Unteres/oberes Muster**: Linien
- **Unteres Muster für erste Schicht**: Linien
- **Reihenfolge des W...drucks optimieren**: leer
- **Lücken zwischen Wänden füllen**: Überall
- **Kleine Lücken ausfiltern**: gesetzt
- **Drucken von dünnen Wänden**: leer
- **Horizontale Erweiterung**: 0 mm
- **EMPFEHLUNG von Cura**:
  - **Glätten aktivieren**: aktivieren
    - es wird mit sehr wenig Extruder-Material noch einmal über die Oberfläche gegangen um mit der Hitze das Material zu glätten


## Füllung

[Füllung](https://youtu.be/wlRO5C9CUb0?t=671)

*wichtiger Punkt*

- **Fülldichte**: 40%
  - je stabiler, desto höher der Wert
  - **Vorsicht** zu hohe Werte lassen das Teil **warpen**
- **Linienabstand Füllung**: 2.0 mm
- **Füllmuster**: Gitter
- **Fülllinie multiplizieren**: 1
- **Prozentsatz Füllung überlappen**: 15%
- **Füllschichtdicke**: 0.15mm
- **Stufenweise Füllungsschritte**: 0


## Material

[Material](https://youtu.be/wlRO5C9CUb0?t=706)

*einer der wichtigsten Einstellungen*

- **Drucktemperatur**: 240
  - entsprechend Heat Tower Ergebnis anpassen (beim Heattower wurde das auf 250 gesetzt)
  - [Thomas](https://youtu.be/8_adY2K-YIc?t=110)
    - hat den Erfahrungswert 230°
    - decrease if
      - excessive **stringing** or
      - **curling** or
      - other overheating artifacts
    - increase if
      - bad layer adhesion
      - extruder jams
- **Drucktemperatur erste Schicht**: 240
- **Anfängliche Drucktemperatur**: 235
- **Endgültige Drucktemperatur**: 225
- **Standardtemperatur Druckplatte**: 80.0
  - Filamentvorgaben berücksichtigen
  - seine 'Lieblingseinstellung'
- **Temperatur Druckplatte**: 80.0
- **Temperatur der Druckplatte die erste Schicht**: 80.0
- **Fluss**: 97%
  - 100% wäre der optimalste Wert
  - Extruder-Kalibrierung spielt hier mit rein
  - wenn das passt geht er erstmal etwas runter mit dem Fluss (3-4%)
    - wenn die Oberflächen nicht richtig geschlossen sein sollten, schrittweise erhöhen
    - wenn die Oberflächen geschlossen sind und nicht schmieren, dann gut
- **Einzug aktivieren**: aktiviert
  - retraction = Einzug
- **Einziehen bei Schichtänderung**: leer
- **Einzugsabstand**: 6mm
  - retraction
  - weil PETG zum **Stringing** neigt hier ein hoher Wert eingestellt
  - 6mm sollte oberste Grenze sein
  - 4mm klappt als unterste Grenze, darunter fängt stringing wieder an
  - [Thomas](https://youtu.be/8_adY2K-YIc?t=127) sagt
    - PETG neigt zu **stringing**
    - **Länge** 1.8mm (Slic3r)
      - increase retract length
      - +1mm für direct Extruder
      - +2-3mm für Bowder
      - zu viel führt zu **blobs**
- **Einzugsgeschwindigkeit**: 45 mm/s
  - wie schnell das Filament eingezogen werden soll
  - dieser Wert ist für ihn ein guter Erfahrungswert
  - [Thomas](https://youtu.be/8_adY2K-YIc?t=127) sagt
    - **Retraction speed** 35mm/s
    - mit dem Wert +/- spielen (25-45)
- **Einzugsgeschwindigkeit (Einzug)**: 45 mm/s
- **Einzugsgeschwin...Zurückschreiben)**: 45 mm/s
- **Mindestbewegung für Einzug**: 1.5mm
  - erst wenn die Nozzle eine Distanz von >1.5mm sich bewegt, dann soll Extruder retraction machen (Filam. einziehen)
- **Maximale Anzahl von Einzügen**: 20
- **Fenster "Minimaler Extrusionsabstand"**: 6mm


## Geschwindigkeit

[Geschwindigkeit](https://youtu.be/wlRO5C9CUb0?t=852)

- **Druckgeschwindigkeit**: 40mm/s
  - eigene Erfahrung: bei niedriegerer Druckgeschwindigkeit ist die Qualität besser
- **Füllgeschwindigkeit**: 40mm/s
- **Wandgeschwindigkeit**: 20.0mm/s
- **Geschwindigkeit Außenwand**: 25mm/s
  - Außenwand ruhig noch etwas langsamerer für ein besseres Druckbild
- **Geschwindigkeit Innenwand**: 40mm/s
- **Geschwindigkei...untere Schicht**: 40mm/s
- **Bewegungsgeschwindigkeit**: 250mm/s
  - **sehr sehr wichtiger Wert**
  - Abhängig von der Firmware
  - bewegt die Nozzle von A nach B so schnell wie möglich
  - das PETG hat dadurch weniger Zeit aus der Spitze herauszulaufen und damit weniger **stringing** oder **blobs**
  - (wahrscheinlich der Wert des Anderen wo der einen hohen Fantasiewert genommen hat)
    - [Thomas](https://youtu.be/8_adY2K-YIc?t=147) sagt:
      - **Speed for non-print moves / Travel** 9001mm/s
      - hoher travel speed between retracts hilft gegen **stringing** und **blobbing**
      - hier kann ein hoher Fantasiewert genommen werden, denn der Drucker reduziert das automatisch auf die max. mögliche Geschwindigkeit
- **Geschwindigkeit der ersten Schicht**: 20.0mm/s
- **Druckgeschwind... erste Schicht**: 15mm/s
  - extrem langsam damit das PETG schön langsam in das 'buildtack'(?) einfließen kann
- **Bewegungsgesc...erste Schicht**: 80mm/s
  - ein bisschen langsamer als er normalerweise seine Spitze bewegt
  - damit die erste Schicht nicht vom Druckbett gerissen wird
- **Geschwindigkeit Skirt/Brim**: 20.0mm/s
  - damit sich die Nozzle schön gemütlich mit PETG füllen kann
- **Beschleunigungssteuerung aktivieren**: leer
  - kann man aktivieren, ist aber kompliziert in den Einstellungen
  - wird evtl. in einem weiteren Video erklärt
- **Rucksteuerung aktivieren**: leer


## Bewegung

[Bewegung](https://youtu.be/wlRO5C9CUb0?t=943)

- **Combing-Modus**: Alle
  - kommt auf das Bauteil an (er hat es meistens an)
  - soll die Spitze bei Bewegung im Bauteil drin bleiben
    - Druck dauert länger
    - dadurch weniger Einzüge
    - weniger chancen **stringing** oder **blobs** zu produzieren
  - oder über freien Raum rüber fahren
- **Gedruckte Teile ...Bewegung umgehen**: aktiviert
- **Stützstrukturen ...Bewegung umgehen**: leer
- **Umgehungsabstand Bewegung**: 0.625mm
- **Z-Sprung beim Einziehen**: leer


## Kühlung

[Kühlung](https://youtu.be/wlRO5C9CUb0?t=983)

- **Kühlung für Drucken aktivieren**: aktiviert
- **Lüfterdrehzahl**: 100.0%
  - Funktioniert bei ihm bei 100% - dadurch evtl. weniger **stringing** oder **blobs**
  - [Thomas](https://youtu.be/8_adY2K-YIc?t=103) sagt
    - **min** 20%, **max** 50% (Slic3r)
- **Normaldrehzahl des Lüfters**: 100.0%
- **Maximaldrehzahl des Lüfters**: 100.0%
- **Grenzwert für Nor..hzahl des Lüfters**: 10%
- **Anfängliche Lüfterdrehzahl**: 0%
  - Lüfter aus, damit sich das PETG schön in das 'bildtag'(?) reingraben kann und nicht zu schnell abkühlt
- **Normaldrehzahl ...üfters bei Höhe**: 0.6mm
- **Normaldrehzahl...rs bei Schicht**: 3
  - ab Schicht 3 wird der Lüfter angeschmissen
- **Mindestzeit für Schicht**: 5
- **Mindestgeschwindigkeit**: 10mm/s
- **Druckkopf anheben**: leer


## Stützstruktur

[Stützstruktur](https://youtu.be/wlRO5C9CUb0?t=1039)

- **Stützstruktur generieren**: leer
  - kommt auf das Modell an
  - **Platzierung Stützstruktur**: Überall
  - **Winkel für Überhänge Stützstruktur**: 50
  - **Muster der Stützstruktur**: Zickzack
  - **Dichte der Stüzstruktur**: 15%
  - **Z-Abstand der Stützstruktur**: 0.1mm
  - **Horizontale Erwei...der Stützstruktur**: 0.2mm
  - **Stützstruktur Füllschichtdicke**: 0.15mm
  - **Stufenweise Füllu...tte Stützstruktur**: 0
  - **Stützstruktur-Schnittstelle aktivieren**: leer
  - **Stützdach aktivieren**: leer
  - **Stützboden aktivieren**: aktiviert
    - **EMPFEHLUNG** von ihm
    - es wird dann zw. Objekt und Stütze eine kleine Platte gedruckt
    - dadurch viel viel saubere Oberflächen! (wenn man die Stütze vom Objekt entfernt)


## Druckplattenhaftung

[Druckplattenhaftung](https://youtu.be/wlRO5C9CUb0?t=1082)

- **Druckplattenhafungstyp**: Skirt
  - meistens skirt
  - wenn Bauteil zu **warping** tendiert dann Brim
    - **Druckplattenhafungstyp**: Brim
    - **Breite des Brim-Elements**: 5mm
    - **Anzahl der Brim-Linien**: 10
    - **Brim nur an Außenseite**: aktiviert
- **Anzahl der Skirt-Linien**: 4
  - wenn neues Material/andere Farbe gewächselt wurde, dann auch mal 10 um die Düse frei zu bekommen
