# Notizen

1. Vorbereitung & Globale Variablen (Global Scope)
Bibliothek einbinden: #include <Keypad.h> nutzen, um die Tasten-Matrix einfach anzusteuern.

Tasten-Layout (Keymap): Ein 2D-Array (char hexaKeys[][]) erstellen, das die Tasten (0-9, A-D, *, #) abbildet.

Pin-Belegung (Pinout):

Pins für die RGB-LED definieren (PWM-Pins für Helligkeitssteuerung).

Pins für Zeilen (Rows) und Spalten (Cols) des Keypads festlegen.

Objekt-Initialisierung: Das Keypad-Objekt mit dem Layout und den Pins erstellen.

Status-Variablen:

int brightness: Speichert die aktuelle Helligkeit (Standard: 255).

String inputString: Ein Puffer für die Zahleneingabe (z.B. "1", "12", "125").

2. Setup-Funktion (void setup)
Pin-Modi: Die LED-Pins als OUTPUT definieren.

Serielle Kommunikation: Serial.begin(9600) starten, um Ausgaben am Monitor zu sehen (Debugging).

Initialisierung: LEDs einmalig beim Start einschalten (optional).

3. Hauptschleife (void loop)
Schritt 1: Eingabe lesen

customKeypad.getKey() aufrufen und das Ergebnis in einer Variable (char customKey) speichern.

Schritt 2: Prüfung auf Tastendruck

if (customKey): Der folgende Code wird nur ausgeführt, wenn tatsächlich eine Taste gedrückt wurde (nicht NO_KEY).

Schritt 3: Modus-Auswahl (Farbe ändern)

Verwendung von switch (customKey) für die Steuerung der Farben:

Case 'A': Roten Kanal aktivieren (mit aktueller Helligkeit), andere ausschalten.

Case 'B': Grünen Kanal aktivieren.

Case 'C': Blauen Kanal aktivieren.

Wichtig: break; nicht vergessen, um den Switch-Block zu verlassen.

Schritt 4: Zahleneingabe (Helligkeit wählen)

if (isDigit(customKey)): Prüfen, ob die Taste eine Ziffer (0-9) ist.

Aktion: Die Ziffer an den inputString anhängen (konkatenieren).

Feedback: Den aktuellen String im Serial Monitor ausgeben.

Schritt 5: Bestätigen / Enter ('#')

else if (customKey == '#'): Die Raute-Taste dient als Enter-Taste.

Validierung: Prüfen, ob inputString nicht leer ist.

Konvertierung: Den String in eine Ganzzahl umwandeln (.toInt()).

Begrenzung (Clamping): Sicherstellen, dass der Wert zwischen 0 und 255 liegt (if > 255 then 255).

Zuweisung: Den Wert in die globale Variable brightness speichern.

Reset: Den inputString leeren, um bereit für die nächste Eingabe zu sein.

Schritt 6: Löschen / Reset ('*')

else if (customKey == '*'): Die Stern-Taste dient zum Korrigieren.

Aktion: Den inputString komplett leeren (""), falls man sich vertippt hat.
