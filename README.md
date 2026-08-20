# D6-Würfeltool

Ein schlankes, generisches Würfelpool-Tool für W6-basierte Systeme. Poolgröße, Erfolgsschwelle und Patzer-Regel frei einstellbar — alles in einer einzigen HTML-Datei. Keine Installation, kein Server, keine Abhängigkeiten.

> Läuft komplett lokal im Browser — deine Daten verlassen das Gerät nicht.

---

## Features

- **🎲 Würfelpool** — 1 bis 20 × W6, Wurf-Animation, Ergebnis pro Würfel farbig markiert.
- **🎯 Erfolgsschwelle** — frei wählbar (2–6): ab welcher Augenzahl ein Würfel als Erfolg zählt.
- **⚠️ Patzer-Regel** — optional, an-/abschaltbar: Patzer, wenn mehr als die Hälfte der Würfel eine 1 zeigt; kritischer Patzer bei Patzer + 0 Erfolgen.
- **💥 Explodierende Sechsen** — optional: jede gewürfelte 6 löst einen zusätzlichen Wurf aus.
- **📜 Verlauf** — die letzten Würfe bleiben sichtbar, inkl. Einzelwürfe.
- **💾 Lokale Speicherung** — Einstellungen und Verlauf bleiben im Browser gespeichert (`localStorage`), kein Server, kein Tracking.

## Schnellstart

1. Repo herunterladen (grüner **Code**-Button → **Download ZIP**) oder klonen.
2. `index.html` im Browser öffnen — fertig. Kein Build, keine Installation.

## Würfel-Logik (Kurzreferenz)

| Ergebnis | Bedeutung |
|---|---|
| ≥ Erfolgsschwelle | Erfolg |
| 1 | zählt für die Patzer-Regel |
| Patzer-Regel aktiv + Einsen > halbe Poolgröße | Patzer |
| Patzer + 0 Erfolge | Kritischer Patzer |

Die Standardwerte (Erfolg ab 5, Patzer-Schwelle bei mehr als der Hälfte Einsen) orientieren sich an einer verbreiteten, generischen Würfelpool-Mechanik und sind an kein bestimmtes Regelwerk gebunden. Beide Werte lassen sich frei anpassen.

## Daten & Datenschutz

Das Tool nutzt ausschließlich den `localStorage` deines Browsers. Es gibt keinen Server, keine Cookies, kein Tracking.

## Über dieses Tool

Entstanden aus dem Bedarf an einem schnellen, werbefreien Würfelpool-Rechner für Tabletop-Runden mit W6-basierten Erfolgssystemen — ohne Server, ohne Tracking, ohne Account. Feedback und Pull Requests willkommen.

— [KopfKinoK3](https://github.com/KopfKinoK3) · [YouTube: Tiny Tactic Tales](https://www.youtube.com/@TinyTacticTales)

## Lizenz

MIT-Lizenz — frei nutzbar, änderbar und weiterverteilbar mit Namensnennung. Siehe [LICENSE](LICENSE).

Dieses Tool ist ein eigenständiges, generisches Würfelpool-Werkzeug ohne Bezug zu einem bestimmten Rollenspiel-Regelwerk oder Verlag.
