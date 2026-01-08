# Projektplan adte (IM5 HS25)

## Rahmen

- Zeitraum: 20.10.25–08.01.26
- Team: Juliette und Sophia
- Ziel: Eine digitale Postkarten-Web-App mit Fokus auf Gestaltung, Teilen per Link/E-Mail und einer klaren, reduzierten UI.

## Meilensteine

- 20.10–02.11: Idee, Scope, Moodboard, erste Wireframes, Repo-Setup
- 03.11–23.11: Architektur + Basis-Implementierung (Vue/Vite, Tailwind, Routing, PocketBase-Schema, Auth-Flow)
- 24.11–14.12: Editor-Kernfunktionen (Front/Back, Elemente, Sticker, Text, Audio, Orientation)
- 15.12–28.12: Teilen + Versand (Share-View, Gallery, Scheduling, E-Mail-Hook)
- 29.12–08.01: Polishing, Responsive Fixes, Doku, Screenshots, Abgabevorbereitung

## Aufgabenverteilung

- Juliette
- Grossteil der Implementierung (UI/UX, Editor, Landing, Galerie, Share-Flow)
  - Integration mit PocketBase (Auth, Datenmodell, Share-Link)
  - Polishing, Responsiveness und Bugfixing
- Sophia
  - Dokumentation (README-Updates, Doku-Inhalte)
  - Text- und Inhaltsanpassungen
- Gemeinsam
  - Konzept, Wireframes, Reviews, Testing und Abgabevorbereitung

## Risiken und Abhängigkeiten

- OAuth-Setup in PocketBase (Google) inkl. Redirect-URLs; ohne korrektes Setup ist Login blockiert
- SMTP/Mailer in PocketBase: notwendig für zeitgesteuerten Versand (Hook `pb_hooks/sendScheduledPostcards.pb.js`)
- PocketBase Schema/Migrations und Dateispeicher (Images/Audio); falsche Felder brechen Create/Share
- Externe APIs für Location/Wetter (BigDataCloud, Open-Meteo): Ausfall oder Rate-Limits
- Canvas-Scaling und Responsiveness (Front/Back, Hoch/Quer) bei kleinen Viewports
- Share-Link/Token-Sicherheit: Token muss korrekt gespeichert und validiert werden

## Definition of Done

- Postkarte kann erstellt werden mit Hintergrund (Upload oder Mood), Text, Sticker, Bild-Overlays
- Audio-Recorder funktioniert (Aufnahme, Abspielen, Speichern in PocketBase)
- Location-Stempel optional und gespeichert (Geo + Wetter, Fallback bei Fehlern)
- Front/Back-Flip und Hoch/Querformat stabil, inkl. Canvas-Scaling
- Speichern in PocketBase mit allen relevanten Feldern (elements, share_token, canvas, theme_id, location)
- Share-Link öffnet die Karte und validiert Token; Galerie zeigt eigene Karten mit Filtern
- Zeitgesteuerter Versand per E-Mail über Hook, setzt `sent` nach Erfolg
- Dokumentation vollständig (README, Plan, Prozess, Screenshots)
