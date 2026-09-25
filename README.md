# client-training-content

Kunden-Inhalte für den `client-training-pdf`-Skill. Dieses Repo enthält
**nur Rohdaten pro Kunde** (Briefing, Screenshots, Design-Tokens) — keine
Rendering-Logik. Die lebt im separaten Skill-Ordner `client-training-pdf/`
(als Claude-Skill unter `skills/` installiert, z. B. in Claude Code oder
Cowork).

## Setup (einmalig)

```bash
# Dieses Repo lokal klonen
git clone <deine-neue-remote-url> client-training-content
cd client-training-content

# Skill installieren (Pfad ggf. anpassen, je nachdem wo dein
# Claude-Code/Cowork-Setup Skills erwartet, z. B. ~/.claude/skills/)
cp -r ../client-training-pdf ~/.claude/skills/client-training-pdf
```

## Neuen Kunden anlegen

```bash
cp -r _template <kundenname>
```

Dann in `<kundenname>/`:
1. `design-tokens.json` ausfüllen (Farben aus SCSS/Figma, siehe `f4t/` als
   Beispiel)
2. `index.md` mit Stichpunkten befüllen (Konvention: siehe
   `client-training-pdf/references/content-conventions.md` im Skill —
   Kurzfassung: Zeilen mit `AUSBAU:` werden von Claude zu vollständigen
   Absätzen ausgebaut, alles andere gilt als fix vorgegeben)
3. Screenshots nach `<kundenname>/screenshots/<thema>/*.png` sortieren
4. Committen + pushen

```bash
git add <kundenname>/
git commit -m "Neuer Kunde: <kundenname>"
git push
```

Dann im Chat: *"Baue das Schulungshandbuch für \<kundenname\>"* — der Skill
übernimmt den Rest.

## Bestehenden Kunden erweitern

- Neue/ersetzte Screenshots einfach in den passenden Unterordner legen
- `index.md` um neue Stichpunkte/Kapitel ergänzen (`AUSBAU:`-Prefix nicht
  vergessen für Dinge, die noch ausformuliert werden sollen)
- Committen, pushen, im Chat Bescheid geben

## Struktur

```
client-training-content/
├── README.md              ← diese Datei
├── _template/              ← Vorlage für neue Kunden (kopieren, nicht editieren)
│   ├── index.md
│   ├── design-tokens.json
│   └── screenshots/        (leer)
└── f4t/                    ← Referenzbeispiel, funktionierend & getestet
    ├── index.md
    ├── design-tokens.json
    ├── _variables.scss     (Quelle der Design-Tokens, zur Nachvollziehbarkeit)
    ├── _mixins.scss
    └── screenshots/
```

`jungmut/` (falls vorhanden) ist ein zweites Test-Beispiel: gleicher
Content wie `f4t/`, aber Design-Tokens live von jungmut.com extrahiert —
zeigt, dass derselbe Content-Code mit komplett anderem Branding
funktioniert. Die Screenshots darin sind zu Testzwecken von F4T
wiederverwendet (nicht echte Jungmut-Screenshots) — vor echter Auslieferung
durch reale Screenshots ersetzen.

## Warum kein Skill-Code in diesem Repo?

Trennung von Engine (Skill, ändert sich selten, gilt für alle Kunden) und
Content (ändert sich ständig, ist pro Kunde). So bleibt eine
Skill-Verbesserung (z. B. neue Bild-Layout-Option) unabhängig vom
Content-Stand jedes einzelnen Kunden versionierbar.
