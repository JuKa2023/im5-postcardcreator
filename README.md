# img-postcardcreator

![Header](docs/header.png)

Ein Projekt von:

- [@JuKa2023](https://github.com/JuKa2023)
- [@SophiaIseli](https://github.com/SophiaIseli)

## Kurzbeschrieb

adte ist eine digitale Postkarten-Webanwendung, mit der Nutzer:innen persönliche Postkarten gestalten und digital versenden können. Der Fokus liegt auf individuellem Ausdruck, bewusster Gestaltung und einer reduzierten, ästhetischen Benutzeroberfläche.

## Features
- Registrierung & Login:
  - Anmeldung und Registrierung über Google-Login

- Inspiration & Einstieg:
  - Frontpage mit Inspirationsinhalten und Beispiel-Postkarten
  - Übersicht über mögliche Gestaltungsstile und Moodrichtungen

- Postkarten erstellen:
  - Upload eigener Bilder und freie Platzierung auf der Postkarte
  - Auswahl von Moodbildern als Hintergrund
  - Textfelder hinzufügen und frei positionieren
  - Auswahl von Schriftarten und Schriftfarben
  - Einfügen von Emojis
  - Aufnahme und Integration einer eigenen Sprachnachricht

- Postkarten versenden & empfangen:
  - Versand digitaler Postkarten
  - Empfang und Ansicht erhaltener Postkarten
  - Generierung eines individuellen Links zur Postkarte
  - Zeitversetztes Versenden mit Datum- und Uhrzeitauswahl
  
- Übersicht & Verwaltung:
  - Ansicht aller selbst erstellten und verschickten Postkarten


## Verwendete Technologien und API

- **Backend & Datenbank**: [PocketBase](https://pocketbase.io/) (Open Source Backend als Service)
  - Verwaltet Authentifizierung (OAuth2 mit Google), Datenbank (SQLite) und Dateispeicherung.

- **Frontend**:
  - **[Vue.js 3](https://vuejs.org/)**: Das progressive JavaScript Framework (verwendet Composition API & `<script setup>`).
  - **[TypeScript](https://www.typescriptlang.org/)**: Für statische Typisierung und bessere Entwickler-Experience.
  - **[Vite](https://vitejs.dev/)**: Next Generation Frontend Tooling.
  - **[Tailwind CSS](https://tailwindcss.com/)**: Ein Utility-First CSS Framework.

- **Listen & Tools**:
  - `vue-router`: Offizieller Router für Vue.js.
  - `pocketbase`: JavaScript SDK für die Backend-Integration.
  - `date-fns`: Moderne Datums-Utility-Bibliothek.
  - `vue-sonner`: Toast-Benachrichtigungen.


## Datenbankstruktur

Das Projekt verwendet ein PocketBase Backend mit einer Haupt-Collection:

### Postcards Collection (postcards)

Die `postcards` Collection speichert alle erstellten Postkarten.

- `front_image` (file): Das Bild der Postkarte.
- `audio` (file, optional): Optionale Sprachnachricht zur Postkarte.
- `message` (text): Die Textnachricht auf der Rückseite.
- `elements` (json): JSON-Array mit den positionierten Elementen (Sticker, Text, etc.).
- `is_public` (bool): Gibt an, ob die Karte in der öffentlichen Galerie sichtbar ist.
- `share_token` (text): Ein eindeutiger Token für den Teilen-Link.
- `sent` (bool): Status, ob die Karte bereits versendet wurde.
- `scheduled_time` (date): Geplanter Versandzeitpunkt (optional).
- `recipient_email` (text): E-Mail-Adresse des Empfängers (optional).
- `user` (relation): Referenz auf den User, der die Karte erstellt hat.

### Users Collection (users)

Die `users` Collection verwaltet die Benutzerkonten der Anwendung.

- `id` (text): Eindeutige ID des Benutzers.
- `email` (email): Die E-Mail-Adresse des Benutzers.
- `emailVisibility` (bool): Gibt an, ob die E-Mail-Adresse für andere sichtbar ist (Standard: False).
- `verified` (bool): Status der E-Mail-Verifizierung.
- `name` (text): Der Anzeigename des Benutzers.
- `avatar` (file): Das Profilbild des Benutzers.
- `created` (date): Zeitstempel der Erstellung (Automatisch).
- `updated` (date): Zeitstempel der letzten Änderung (Automatisch).

## Setup

Für die Einrichtung des Projekts empfehlen wir die Verwendung von Docker, da dies die Installation und Konfiguration aller benötigten Komponenten vereinfacht:


### Umgebungsvariablen

Die Anwendung verwendet folgende Umgebungsvariablen:

- `DB_HOST`: Datenbank-Host (Standard: mysql)
- `DB_NAME`: Datenbankname (Standard: im3)
- `DB_USER`: Datenbankbenutzer (Standard: root)
- `DB_PASSWORD`: Datenbankpasswort
- `DB_ROOT_PASSWORD`: Root-Passwort
- `APP_ENV`: Anwendungsumgebung (Entwicklung/Produktion)
- `APP_DEBUG`: Debug-Modus (true/false)

## Reflektion

Nachfolgend einige reflektierende Gedanken und Erkenntnisse, die sich aus den Erfahrungen des Projekts ergeben haben:

### Learnings

- APIs integrieren und verknüpfen: Wir haben gelernt, wie man APIs untersucht und welche Tücken sie mitbringen können, wie man verschiedene APIs (Wetter- und Zugverspätungsdaten) nahtlos in eine Webanwendung integriert und die Daten sinnvoll kombiniert, wann es Sinn macht Daten vorab in eine Datenbank zu speichern.
- Datenanalyse und Visualisierung: Einblicke in die Korrelation von Wetterbedingungen und Verspätungen auf den Strecken wurden durch statistische Auswertungen und die Visualisierung der Ergebnisse gewonnen.
- Benutzerzentrierte Gestaltung: Wir haben den Fokus darauf gelegt, die Anwendung für den Benutzer einfach und interaktiv zu gestalten.

### Schwierigkeiten

4. **Frontend-Entwicklung und Responsivität:**
   - Gestaltung einer responsiven Benutzeroberfläche mit Tailwind CSS
   - Anpassung des Layouts für verschiedene Bildschirmgrössen

### Benutzte Ressourcen

Während der Entwicklung des Projekts traten verschiedene technische Herausforderungen auf. In einem ersten Schritt griffen wir auf unsere Unterrichtsnotizen sowie das bereitgestellte Kursmaterial zurück. Diese bildeten die Grundlage für viele architektonische und konzeptionelle Entscheidungen.

Wenn das Kursmaterial keine ausreichende Lösung bot, nutzten wir zusätzliche Online-Ressourcen. Für backend- und datenbankbezogene Funktionen verwendeten wir hauptsächlich die offizielle Dokumentation von [PocketBase](https://pocketbase.io/docs/). Für die Umsetzung des Frontends mit Vue.js orientierten wir uns an der offiziellen [Vue.js-Dokumentation](https://vuejs.org/).

Zur Unterstützung bei konkreten Codeproblemen und zur Klärung von Verständnisfragen setzten wir KI-gestützte Tools wie [ChatGPT](https://chat.openai.com/) und [Claude](https://claude.ai/new) ein. Diese dienten insbesondere als Hilfe bei der Fehlersuche, beim Refactoring sowie beim Verständnis komplexerer Logik, ohne den eigentlichen Entwicklungsprozess vollständig zu automatisieren.

Für allgemeine Programmierkonzepte und Syntaxfragen griffen wir ergänzend auf Plattformen wie [W3Schools](https://www.w3schools.com/) zurück.

Im Bereich Design und Styling nutzten wir primär die offizielle Dokumentation von [Tailwind CSS](https://tailwindcss.com/), um Utility-Klassen korrekt einzusetzen und ein konsistentes Layout umzusetzen. Als visuelle Inspiration für das Design und die Benutzeroberfläche diente unter anderem die Plattform [Pinterest](https://www.pinterest.com/).

Bei komplexeren Fragestellungen oder konzeptionellen Unsicherheiten zogen wir bewusst menschliche Unterstützung hinzu. In diesen Fällen erhielten wir wertvolle Hilfe durch unsere Dozenten sowie durch Freunde mit Erfahrung in der Softwareentwicklung.

### Erweiterungsmöglichkeiten

- **Postkarten-Konversationen**
  - Beantworten empfangener Postkarten entweder mit:
    - einer Textnachricht oder
    - einer neuen Postkarte
  - Darstellung der Antworten in einer Chat-ähnlichen Ansicht (ähnlich zu WhatsApp)
  - Übersicht über alle ausgetauschten Postkarten und Reaktionen zwischen zwei Nutzer:innen

- **Erweiterte Medienunterstützung**
  - Unterstützung von Video-Postkarten
  - Integration von animierten Elementen (z. B. GIFs)

- **Persönliche Galerien**
  - Eigene Galerie empfangene Postkarten
  - Option, eine Galerie oder Postkarte zu veröffentlichen
  - Erneutes Versenden oder Herunterladen empfangener Postkarten

- **Community- & Sharing-Funktionen**
  - Veröffentlichen von Postkarten-Designs und Templates
  - Andere Nutzer:innen können Designs anpassen oder weiterentwickeln
  - Anzeige der ursprünglichen Urheber:innen bei wiederverwendeten Designs
  - Liken, Speichern oder Markieren von Favoriten

- **Interaktionen & Reaktionen**
  - Emoji-Reaktionen auf Postkarten
  - Kommentarfunktion (privat oder öffentlich)
  - Zustell- und Lesebestätigungen

- **Performance & Skalierbarkeit**
  - Bild- und Videokomprimierung für schnellere Uploads
  - Caching häufig genutzter Designs
  - Optimierung der Cloud-Speicherung

### Bugs

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
