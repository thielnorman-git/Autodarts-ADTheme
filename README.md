🎯 Autodarts Gold-Glow Theme

Dieses Repository bietet ein exklusives Design-Upgrade für Autodarts. Durch die Nutzung der Stylebot Erweiterung wird die Standard-Oberfläche in ein modernes, dunkles Interface mit edlen Gold-Effekten verwandelt.

✨ Highlights

Dynamischer Fokus: Der aktive Spieler leuchtet goldgelb und pulsiert leicht – so verpasst du nie, wer an der Reihe ist.

Glasmorphismus: Semi-transparente Boxen mit Unschärfe-Effekt (backdrop-filter) für einen High-End-Look.

Smart Layout: Automatische Anpassung der Spielerboxen (1-6 Spieler), um den Platz optimal zu nutzen.

Custom Background: Ein atmosphärischer Hintergrund, der das Dart-Feeling direkt in den Browser holt.

📸 Screenshots

![autodartsbg](https://github.com/user-attachments/assets/facb5fee-f31f-48b4-b103-05d4233bcdf9)

🛠️ Installation via Stylebot

1. Erweiterung installieren
Installiere die Stylebot Browser-Erweiterung für deinen Browser:

Chrome Web Store

Firefox Add-ons

Microsoft Edge Add-ons

1. Konfiguration importieren

Kopiere das folgende JSON-Snippet vollständig in deine Zwischenablage:
```
{
  "play.autodarts.io": {
    "css": ":root {\n  --color-bg-main: rgba(20, 20, 20, 0.9);\n  --color-bg-box: linear-gradient(145deg, rgba(45, 45, 45, 0.9), rgba(10, 10, 10, 0.95));\n  --color-border-inactive: rgba(180, 160, 120, 0.4);\n  /* Goldgelb-Palette für den aktiven Spieler */\n  --active-gold: #ffcc00;\n  --active-gold-bright: #ffe500;\n  --active-gold-glow: rgba(255, 204, 0, 0.7);\n  --color-text: #f5f5f0;\n  --font-main: 'Montserrat', sans-serif;\n  --spacing-player: 20px;\n  --row-height-3: calc((108% - 180px) / 3 - var(--spacing-player));\n}\n\n/* --- FORCE ANIMATION LOGIC --- */\n@keyframes goldGlowPulse {\n  0% {\n    box-shadow: 0 0 15px var(--active-gold-glow) !important;\n    border-color: var(--active-gold) !important;\n    transform: scale(1.03);\n  }\n  50% {\n    box-shadow: 0 0 45px var(--active-gold), inset 0 0 15px rgba(255, 255, 255, 0.2) !important;\n    border-color: #ffffff !important;\n    transform: scale(1.05);\n  }\n  100% {\n    box-shadow: 0 0 15px var(--active-gold-glow) !important;\n    border-color: var(--active-gold) !important;\n    transform: scale(1.03);\n  }\n}\n\n/* --- Globaler Hintergrund --- */\nbody {\n  background-image: url(https://i.ibb.co/qLrdmYGc/bg.jpg) !important;\n  background-size: cover !important;\n  background-position: center !important;\n  background-attachment: fixed !important;\n}\n\n/* --- Spielerboxen Basis (Inaktiv) --- */\n:root:not(:has(.css-rc3vw3)) .css-rtn29s,\n:root:not(:has(.css-rc3vw3)) .css-hjw8x4 {\n  background: var(--color-bg-box) !important;\n  color: var(--color-text) !important;\n  border: 1px solid var(--color-border-inactive);\n  backdrop-filter: blur(10px);\n  border-radius: 12px;\n  position: absolute;\n  width: 400px;\n  height: calc((100% - 180px) / 3);\n  transition: all 0.3s ease-in-out;\n}\n\n/* --- AKTIVER SPIELER: GOLDGELB & PULSIEREND --- */\n:root:not(:has(.css-rc3vw3)) .css-rtn29s,\n[class*=\"active-player\"],\n.ad-ext-player.active {\n  z-index: 100 !important;\n  background: linear-gradient(145deg, #2a2a00, #000000) !important;\n  border: 3px solid var(--active-gold) !important;\n  animation: goldGlowPulse 1.5s infinite ease-in-out !important;\n}\n\n/* Texte beim aktiven Spieler */\n:root:not(:has(.css-rc3vw3)) .css-rtn29s .css-1j0bqop,\n:root:not(:has(.css-rc3vw3)) .css-rtn29s .css-1r7jzhg {\n  color: var(--active-gold) !important;\n  text-shadow: 0 0 12px rgba(255, 204, 0, 0.8) !important;\n  font-weight: 900 !important;\n}\n\n/* --- Scoring Bereich --- */\n:root:not(:has(.css-rc3vw3)) #ad-ext-turn .css-rrf7rv,\n:root:not(:has(.css-rc3vw3)) #ad-ext-turn .score.css-156dsds,\n:root:not(:has(.css-rc3vw3)) #ad-ext-turn .ad-ext-turn-throw.css-1p5spmi {\n  background: rgba(15, 15, 15, 0.9) !important;\n  border: 1px solid var(--color-border-inactive);\n  border-radius: 10px;\n  height: 120px;\n  color: #fff !important;\n}\n\n/* --- Layout-Positionierung (1-6 Spieler) --- */\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(1):only-child {\n  top: 90px;\n  left: 60px;\n  height: calc(100% - 180px);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(1):nth-last-child(2) {\n  top: 90px;\n  left: 60px;\n  height: calc(100% - 200px);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(2):nth-last-child(1) {\n  top: 90px;\n  right: 60px;\n  height: calc(100% - 200px);\n}\n\n/* 3-4 Spieler */\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(1):nth-last-child(3),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(1):nth-last-child(4) {\n  top: 90px;\n  left: 60px;\n  height: calc((105% - 180px) / 2 - var(--spacing-player));\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(2):nth-last-child(2),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(2):nth-last-child(3) {\n  top: 90px;\n  right: 60px;\n  height: calc((105% - 180px) / 2 - var(--spacing-player));\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(3):nth-last-child(1),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(3):nth-last-child(2) {\n  top: calc(90px + ((100% - 180px) / 2) + var(--spacing-player));\n  left: 60px;\n  height: calc((105% - 180px) / 2 - var(--spacing-player));\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(4):last-child {\n  top: calc(90px + ((100% - 180px) / 2) + var(--spacing-player));\n  right: 60px;\n  height: calc((105% - 180px) / 2 - var(--spacing-player));\n}\n\n/* 5-6 Spieler */\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(1):nth-last-child(5),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(1):nth-last-child(6) {\n  top: 90px;\n  left: 60px;\n  height: var(--row-height-3);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(2):nth-last-child(4),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(2):nth-last-child(5) {\n  top: 90px;\n  right: 60px;\n  height: var(--row-height-3);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(3):nth-last-child(3),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(3):nth-last-child(4) {\n  top: calc(90px + ((100% - 180px) / 3) + var(--spacing-player));\n  left: 60px;\n  height: var(--row-height-3);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(4):nth-last-child(2),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(4):nth-last-child(3) {\n  top: calc(90px + ((100% - 180px) / 3) + var(--spacing-player));\n  right: 60px;\n  height: var(--row-height-3);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(5):nth-last-child(1),\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(5):nth-last-child(2) {\n  top: calc(90px + 2 * ((100% - 180px) / 3) + 2 * var(--spacing-player));\n  left: 60px;\n  height: var(--row-height-3);\n}\n:root:not(:has(.css-rc3vw3)) #ad-ext-player-display > div:nth-child(6):last-child {\n  top: calc(90px + 2 * ((100% - 180px) / 3) + 2 * var(--spacing-player));\n  right: 60px;\n  height: var(--row-height-3);\n}\n\n/* Menüs & Badges */\nspan.chakra-badge.css-n2903v {\n  font-size: 20px;\n  color: var(--active-gold) !important;\n  background: rgba(0, 0, 0, 0.6) !important;\n}\n\n[id^=\"menu-list-\"] {\n  background: #111 !important;\n  border: 1px solid var(--active-gold) !important;\n  border-radius: 12px;\n}",
    "readability": false,
    "enabled": true,
    "modifiedTime": "2026-03-28T10:49:51.850+01:00"
  }
}
```
2. Klicke auf das Stylebot-Icon in deiner Browser-Leiste und wähle Options.

3. Navigiere im linken Menü zu Backup.

4. Klicke auf den Button Import.

5. Füge den kopierten Code in das Textfeld ein und bestätige mit Import.

🔍 Troubleshooting (Fehlerbehebung)

Frage: Der Style wird auf play.autodarts.io nicht geladen.

Lösung: Klicke auf das Stylebot-Icon während du auf der Seite bist. Stelle sicher, dass der Hauptschalter oben rechts im Stylebot-Fenster auf "On" steht und der Eintrag für play.autodarts.io markiert ist.

Frage: Die Animation ruckelt oder die Schrift sieht anders aus.

Lösung: Dieses Design verwendet die Schriftart 'Montserrat'. Falls diese auf deinem System nicht installiert ist, wird eine Standard-Serifenlose Schrift verwendet. Die Animation (goldGlowPulse) benötigt Hardwarebeschleunigung im Browser für eine flüssige Darstellung.

Frage: Die Boxen überlappen sich bei vielen Spielern.

Lösung: Das Layout ist für gängige Full-HD Auflösungen optimiert. Wenn du ein sehr kleines Fenster oder extremes Zoom-Level nutzt, kann es zu Verschiebungen kommen. Nutze Strg + 0, um den Zoom zurückzusetzen.

🎨 Eigene Anpassungen

Du möchtest eine andere Farbe statt Gold? Suche im CSS-Bereich von Stylebot nach diesen Variablen und ändere die Hex-Codes:

--active-gold: Die Hauptfarbe des aktiven Spielers.

background-image: Ersetze die URL durch dein eigenes Hintergrundbild.

Viel Spaß beim Darten.
