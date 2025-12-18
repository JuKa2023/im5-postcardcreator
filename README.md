# img-postcardcreator

![Header](docs/header.png)

Ein Projekt von:

- [@JuKa2023](https://github.com/JuKa2023)
- [@SophiaIseli](https://github.com/SophiaIseli)

## Features

## Verwendete Technologien und API
- Backend: PHP für Datenverarbeitung und API-Entwicklung

- Datenbank: MariaDB für effiziente Datenspeicherung und -verwaltung

- Frontend:
  - HTML für die Struktur der Webseite
  - Tailwind CSS für responsives und modernes Design
  - JavaScript für interaktive Elemente und Datenvisualisierung

- Diagramme: Chart.js für die Erstellung interaktiver und anpassbarer Grafiken

- APIs:
  - Open-Meteo API für Wetterdaten
  - OpenTransport API für Zugverspätungsinformationen

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

Während der Entwicklung stiessen wir auf technische Herausforderungen. In solchen Fällen griffen wir auf die Notizen aus dem Unterricht zurück. Wenn uns das Kursmaterial nicht weiterhalf, griffen wir auf [ChatGPT](https://chat.openai.com/) und [W3Schools](https://www.w3schools.com/php/default.asp) zurück, um Lösungen für Codeprobleme zu finden und uns bei Unklarheiten in der Programmierung zu unterstützen. Diese Vorgehensweise trug wesentlich zur Effizienz und Qualität des Entwicklungsprozesses bei. Natürlich gab es auch immer wieder Punkte, wo wir lieber auf menschliche Hilfe zurückgreifen wollten. In diesen Fällen erhielten wir Unterstützung durch unsere Dozenten oder Freunde, die in der Programmierwelt eingebettet sind.

Für Design-Inspirationen haben wir häufig die Seite CodePen [CodePen](https://codepen.io/) genutzt. Diese Plattform erfordert jedoch eine gewisse Menge an Fachjargon und Vorwissen, um die gewünschten Ergebnisse zu finden. Es ist wichtig, klar anzugeben, mit welchen Technologien man arbeitet und ob man bestimmte Frameworks verwendet oder nicht, um relevante und nützliche Beispiele zu finden. Für Pragen bezüglich des Designs mit Tailwind, griffen wir auf die offizielle Entwicklerseite zurück [TailwindCSS](https://tailwindcss.com/).

### Erweiterungsmöglichkeiten

### Bugs


This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VS Code](https://code.visualstudio.com/) + [Vue (Official)](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Recommended Browser Setup

- Chromium-based browsers (Chrome, Edge, Brave, etc.):
  - [Vue.js devtools](https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd) 
  - [Turn on Custom Object Formatter in Chrome DevTools](http://bit.ly/object-formatters)
- Firefox:
  - [Vue.js devtools](https://addons.mozilla.org/en-US/firefox/addon/vue-js-devtools/)
  - [Turn on Custom Object Formatter in Firefox DevTools](https://fxdx.dev/firefox-devtools-custom-object-formatters/)

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

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
