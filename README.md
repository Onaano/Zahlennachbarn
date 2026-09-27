# 🏘️ Zahlennachbarn — „Wer wohnt nebenan?"

Ein Lernspiel zu Zahlenfolgen und Zahlennachbarschaften: Zahlen wohnen als
Hausnummern nebeneinander in einer freundlich illustrierten Zahlenstraße.

**Zielgruppe:** Klasse 1–3, Förderunterricht
**Status:** Version 1.0

## 🏠 Die drei Zahlenräume

- **bis 20** — Klasse 1
- **bis 100** — Klasse 2
- **bis 1000** — Klasse 3

Jeder Bereich nutzt eine passende Auswahl an Aufgabentypen (siehe unten) —
Nachbarzehner erst ab „bis 100", Nachbarhunderter nur bei „bis 1000".

## 🧩 Sechs Aufgabentypen

1. **Wer wohnt nebenan?** — Vorgänger und Nachfolger einer Zahl finden
2. **Welches Haus fehlt?** — eine von drei aufeinanderfolgenden Hausnummern
   fehlt (beliebige Position)
3. **Welche Straße stimmt?** — von drei Zahlenfolgen ist nur eine korrekt
   aufeinanderfolgend
4. **Finde die Nachbarzehner** — z. B. 64 → 60 / 70 (bis 100, bis 1000)
5. **Finde die Nachbarhunderter** — z. B. 347 → 300 / 400 (nur bis 1000)
6. **Wer wohnt zwei Häuser weiter?** — wie Typ 2, andere Formulierung/Kontext

Volle Zehner bzw. Hunderter werden korrekt als Sonderfall behandelt: bei
50 sind die Nachbarzehner 40 und 60 (nicht 50 und 60), bei 500 sind die
Nachbarhunderter 400 und 600 (nicht 500 und 600).

Eine Runde besteht aus 8 richtig gelösten Aufgaben, sichtbar als
beleuchtete Häuser in der Fortschrittsanzeige. Kein Punktabzug, keine
Zeitbegrenzung, keine Leben — bei einer falschen Antwort gibt es eine
freundliche Rückmeldung und die Aufgabe bleibt bestehen.

## 🛠️ Technik

Eine einzige, in sich geschlossene `index.html`-Datei — kein Build-Prozess,
keine Abhängigkeiten, kein Server nötig.

- Reines HTML, CSS und JavaScript (kein Framework)
- Häuser als parametrisierte SVGs (mehrere Dach-/Fenster-/Fassadenvarianten,
  keine externen Bilddateien)
- Sprachausgabe optional über den Lautsprecher-Button (native
  `SpeechSynthesis`-API), rein manuell, kein automatisches Vorlesen
- Distraktoren bei Multiple-Choice-Aufgaben werden über eine enge und eine
  breitere Rückfall-Suche erzeugt und explizit gegen Duplikate sowie eine
  versehentlich zweite korrekte Option geprüft
- Sicherheitsnetz: löst sich ein interner Sperr-Zustand durch einen
  unerwarteten Fehler nicht rechtzeitig, wird er nach wenigen Sekunden
  automatisch freigegeben
- Läuft vollständig offline, keine externen Ressourcen
- Responsiv für Smartboard, Desktop, Tablet und Smartphone
- Keine personenbezogenen Daten, keine Cookies, kein Tracking

## 📁 Projektstruktur

```
zahlennachbarn-projekt/
├── index.html      ← das komplette Spiel
├── README.md
└── .gitignore
```

## ▶️ Lokal ausprobieren

Einfach `index.html` im Browser öffnen — kein Server, keine Installation
nötig.

## 🌐 Veröffentlichung

### GitHub
1. Neues Repository auf [github.com](https://github.com) anlegen.
2. `index.html`, `README.md` und `.gitignore` hochladen.

### Netlify (per Drag & Drop)
1. Auf [app.netlify.com](https://app.netlify.com) einloggen.
2. Den Projektordner direkt in den Browser ziehen („Deploy manually").
3. Netlify vergibt sofort einen Link. Build command: leer, Publish
   directory: `.`

## ✅ Qualitätssicherung

- Alle in der Spezifikation genannten Sonderfälle für Nachbarzehner und
  Nachbarhunderter einzeln geprüft (u. a. 50→40/60, 99→90/100, 100→90/110,
  500→490/510 bzw. 500→400/600, 599→500/600, 600→500/700, 999→900/1000)
- 180 automatisiert erzeugte Aufgaben über alle drei Bereiche geprüft:
  0 Fehler bei Zahlenraum-Grenzen, Distraktor-Eindeutigkeit, korrekter
  Antwort in den Optionen und exakter Optionsanzahl
- Volle Runden (8/8) in allen drei Bereichen erfolgreich getestet
- Doppelklick/Doppeltipp auf eine richtige Antwort vergibt nur einmal
  Fortschritt
- Alle 6 vorgeschriebenen Bildschirmgrößen (375×667 bis 1920×1080)
  geprüft: kein horizontales Scrollen, Aufgabe vollständig sichtbar

## 📄 Lizenz

© Förderfreude Games. Alle Rechte vorbehalten.
