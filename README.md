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

## SR-3D-Player für GLB-Karten

`3d-player.html` (SR-3D-Player) ist ein eigenständiger Betrachter für 3D-Karten im GLB-Format, gedacht für die Spieler am Tisch. Er hat keine Verbindung zum Würfeltool.

**Start:** `3d-player.html` per Doppelklick im Browser öffnen (Safari ab 16.4, Chrome, Firefox). Dann „Karte laden“ wählen oder eine `.glb`-Datei ins Fenster ziehen. Die Datei wird nur lokal gelesen, nichts wird hochgeladen. Beim ersten Öffnen braucht der Browser Internet, weil three.js in fester Version (0.185.1) von jsDelivr geladen wird.

**Stationen:** Rechts stehen die Blickwinkel aus der Karte. Ein Klick fährt die Kamera in 5 Sekunden weich dorthin. „Gesamtansicht“ zeigt die ganze Karte. Ein Blickwinkel entsteht in Blender aus zwei leeren Objekten:

| Objekt | Bedeutung |
|---|---|
| `Kamera_<Name>` | Standort der Kamera |
| `Kamera_<Name>_Ziel` | Punkt, auf den sie schaut (fehlt er, schaut sie 10 m entlang ihrer −Z-Achse) |

Unterstriche im Namen werden zu Leerzeichen (`Kamera_Lidl_Dach` heißt „Lidl Dach“). Die Reihenfolge folgt der Datei.

**Animationen:** Jede in der GLB eingebaute Animationsspur bekommt einen Knopf zum Abspielen und Stoppen. Sie läuft in Schleife.

Dazu kommen bewegliche Teile ohne Animationsspur: ein Objekt `X` plus ein leeres Objekt `X_Draussen`. Dessen Lage ist die Mitte von `X`, wenn es „draußen“ steht. Ein Klick fährt `X` in 6 Sekunden dorthin und blendet es aus, der nächste Klick holt es zurück. Optionale Custom Properties am `_Draussen`-Objekt: `label` (Knopftext), `verbAus` und `verbEin` (z. B. „hebt ab“ / „senkt sich“), `reihenfolge` (Zahl) und `start` = `draussen` (beim Laden schon draußen). Teile mit `geheim` = `true` sind nur für die Spielleitung: Der Player zeigt für sie keinen Knopf, sie bleiben an ihrem Halt.

**Steuerung:**

| Eingabe | Wirkung |
|---|---|
| Maus links ziehen | um das Ziel drehen |
| Maus rechts ziehen | schieben |
| Mausrad | zoomen |
| Pfeiltasten | Kamera über den Boden fahren (halten für längere Fahrt) |
| `-` / rechte Umschalttaste | Blick nach links / rechts drehen |
| `1` bis `9`, `0` | Station anfahren, Gesamtansicht |

Auf dem Handy oder Tablet: ein Finger dreht, zwei Finger zoomen und schieben. Bei schmalen Fenstern rutscht die Liste unter das Bild.

**Falls der Doppelklick nicht reicht:** Blockiert ein Browser Skripte aus lokalen Dateien, im Ordner des Repos einen kleinen Server starten und `http://localhost:8000/3d-player.html` öffnen:

```bash
python3 -m http.server 8000
```

## Daten & Datenschutz

Das Tool nutzt ausschließlich den `localStorage` deines Browsers. Es gibt keinen Server, keine Cookies, kein Tracking.

## Über dieses Tool

Entstanden aus dem Bedarf an einem schnellen, werbefreien Würfelpool-Rechner für Tabletop-Runden mit W6-basierten Erfolgssystemen — ohne Server, ohne Tracking, ohne Account. Feedback und Pull Requests willkommen.

— [KopfKinoK3](https://github.com/KopfKinoK3) · [YouTube: Tiny Tactic Tales](https://www.youtube.com/@TinyTacticTales)

## Lizenz

MIT-Lizenz — frei nutzbar, änderbar und weiterverteilbar mit Namensnennung. Siehe [LICENSE](LICENSE).

Dieses Tool ist ein eigenständiges, generisches Würfelpool-Werkzeug ohne Bezug zu einem bestimmten Rollenspiel-Regelwerk oder Verlag.
