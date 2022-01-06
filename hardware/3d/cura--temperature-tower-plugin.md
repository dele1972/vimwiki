1. Erweiterungen | Part for calibration / Add a PLA TempTower
2. Profil: Draft 0.2mm
3. Slice
4. Vorschau: notiere die Schicht des Sockels (bevor die ersten Tower Quadrate gedruckt werden) - bei mir: 3
5. Vorschau: notiere die oberste Schicht - bei mir 378
6. entweder:
    - Erweiterung | Nachbearbeitung | G-Code ändern auswählen oder
    - den Button `</>` mit der roten (1) - links neben dem Slice/Auf Festplatte speichern Button klicken
    - BEIM ERSTEN AUFRUF muss das Skript erst hinzugefügt werden
        - Erweiterung | Nachbearbeitung | G-Code ändern auswählen → Button Ein Skript hinzufügen klicken und `TempFanTower` hinzufügen
7. Im Script TempFanTower die Werte anpassen
    - Vorab - Berechnung wie viele Layer ein Abschnitt umfasst
        - (MAX-LAYER - SOCKEL) / ANZAHL-ELEMENTE
            - SOCKEL siehe __Punkt 4__
            - MAX-LAYER siehe __Punkt 5__
        - (378-3) / 9 → 41,666 → 41
    - Starting Temperature [220]: die Starttemperatur des Towers - hier: 220
    - Temperature Increment [-5]: um wieviel Grad sich die Temperatur pro Abschnitt ändern soll - hier: -5
    - Change Layer [52.0]: wie viele Layer umfasst ein Abschnitt - hier: 41
    - Change Layer Offset [5.0]:
    - Activate Fan Tower []:
8. Profile: Material - Einstellungen vornehmen
    - Printing Temperature → Höchste Temperatur des Towers angeben - hier: 220
    - Printing Temperature Initial Layer → Höchste Temperatur des Towers angeben - hier: 220
    - Printing Printing Temperature → Höchste Temperatur des Towers angeben - hier: 220
    - Final Printing Temperature → Höchste Temperatur des Towers angeben - hier: 220
9. Slice, Datei speichern und zum Drucker
