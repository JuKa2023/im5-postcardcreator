# Projektprozess (wöchentlich)

Zeitraum: 20.10.25–08.01.26
Team: Juliette und Sophia

## Coaching

Wir waren während der Planungsphase regelmässig im Coaching, vor allem bei der Basis-Idee, der Kernlogik und dem ersten Datenbankschema. Später sind wir nicht mehr ins Coaching gegangen, da es keine Unterrichtstermine mehr gab und wir vieles direkt im Doing gelernt haben.

### KW 1 (20.10.25–26.10.25)

- Kick-off, Projektidee geschärft, Funktionsumfang grob abgegrenzt
- Visuelle Richtung definiert (Moodboard, Referenzen)
- Repo angelegt, Grundsetup für Vue/Vite vorbereitet

wir haben bewusst klein gestartet, damit der scope realistisch bleibt. erste referenzen gesammelt und die postkarten-ästhetik festgelegt.
Wir haben eine einfache Aufgabenliste im Repo angelegt und erste Skizzen für die Editor-Flows gemacht.

### KW 2 (27.10.25–02.11.25)

- Wireframes und erste User-Flow-Skizzen
- UI-Richtung festgelegt (Typografie, Farben, Karten-Look)
- PocketBase lokal aufgesetzt, Schema-Entwurf gestartet

Wir haben den Flow "create -> save -> share" priorisiert und die Screens grob sortiert.
Parallel wurden erste Schema-Felder notiert, damit Bild, Audio und Elemente später sauber gespeichert werden.

### KW 3 (03.11.25–09.11.25)

- Routing und Grundstruktur der App aufgebaut
- Landing Page Skeleton umgesetzt
- OAuth-Login (Google) in PocketBase konfiguriert

Erste klickbare Strecke stand, Login wurde getestet. Dabei gab es kleinere OAuth-Stolpersteine, die wir direkt bereinigt haben.
Landing-Texte wurden grob gesetzt, um Ton und Stimmung der Marke zu prüfen.

### KW 4 (10.11.25–16.11.25)

- Postcard-Canvas Basis gebaut (Scaling, Stage, Flip)
- Front/Back-Struktur angelegt
- Orientation (Hoch/Quer) konzipiert

Der Canvas-Scaling Teil war knifflig, vor allem für mobile. Wir haben früh gemerkt, dass die Kartenlogik sauber getrennt sein muss.
Wir haben mehrere Grössen getestet und die ersten Bugs für das Scaling gesammelt.

### KW 5 (17.11.25–23.11.25)

- Elemente-Handling (Text, Sticker) implementiert
- Bilder als frei platzierbare Overlays integriert
- Erste Controls für Schriftgrösse/Farbe ergänzt

Drag/Resize war iterativ: Gefühl prüfen, Griffe anpassen, nochmal testen. Die Elemente müssen leicht wirken, ohne zu fliegen.
Wir haben Löschen, Fokus und das Speichern der Elementdaten stabilisiert.

### KW 6 (24.11.25–30.11.25)

- Audio-Recorder integriert
- Backside-Layout und Themes für Rückseite umgesetzt
- Location-Stempel-Prototyp (Geo + Wetter) vorbereitet

War eine eher experimentelle Woche, weil Audio viele States braucht. Der Location-Stempel war schnell sichtbar, aber Fehlerfälle mussten wir abfangen.
Wir haben Playback, Aufnahme und Reset durchgespielt, damit die UI nicht hängt.

### KW 7 (01.12.25–07.12.25)

- Share-Link-Logik und Shared View aufgebaut
- Galerie für eigene Karten umgesetzt (Filter/Preview)
- Canvas-Datenmodell verfeinert

erstes end-to-end: erstellen -> speichern -> teilen. das hat die wichtigsten kantenfälle gezeigt (token, bild-urls, scaling).
Die Galerie wurde mit dem Polaroid-Look abgestimmt, damit die Previews konsistent wirken.

### KW 8 (08.12.25–14.12.25)

- Versand-Modal mit Scheduling + Recipient E-Mail
- PocketBase Hook für zeitgesteuerten Versand integriert
- Env-Variablen und Versand-Flow abgestimmt

Hier wurde das Datum-Format wichtig, damit Scheduling konsistent bleibt. Der Mailer-Hook brauchte ein paar Anläufe, bis der Flow stabil war.
Wir haben Testmails mit dem PocketBase Mailer geprüft und die Fehlermeldungen geloggt.

### KW 9 (15.12.25–21.12.25)

- Landing Page animiert und Inhalte ergänzt
- lokale Inspirationsgalerie ergänzt
- UI-Feinschliff an Komponenten

Wir haben mehr aufs Gefühl geachtet: Animationen, Abstände, Typografie. Kleine Details machen die Seite fertig.
Die Landing wurde inhaltlich gestrafft, damit der CTA klar bleibt.

### KW 10 (22.12.25–28.12.25)

- Responsive Fixes im Editor und Share-View
- Bugfixes im Element-Handling
- Share-Ansicht visuell finalisiert

War eine bugfix-lastige Woche. Besonders Mobile-Ansichten und das Centering im Share View mussten sauber sitzen.
Wir haben den Editor auf kleineren Viewports getestet und die Abstände korrigiert.

### KW 11 (29.12.25–04.01.26)

- Stabilisierung, Cleanup, kleinere UX-Verbesserungen
- Dokumentationsentwurf vorbereitet
- Screenshot-Plan erstellt

wir haben bewusst nichts neues mehr angefangen. fokus lag auf stability und der doku-struktur.
Wir haben offene Bugs priorisiert und die letzten UI-Kanten geglättet.

### KW 12 (05.01.26–08.01.26)

- Dokumentation finalisiert (README, Plan, Prozess)
- Screenshots erstellt
- Finaler Review und Abgabevorbereitung

Letzte Checks, ein paar offene Kanten geschlossen. Abgabe Paket final gemacht und alles konsistent gezogen.
Wir haben die Doku finalisiert und die Screenshots aktualisiert.
