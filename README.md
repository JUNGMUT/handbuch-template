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
1. `index.md` mit Stichpunkten befüllen oder an die neuen Anforderungen anpassen (Konvention: siehe `client-training-pdf/references/content-conventions.md` im Skill — Kurzfassung: Zeilen mit `AUSBAU:` werden von Claude zu vollständigen Absätzen ausgebaut, alles andere gilt als fix vorgegeben)
2. Screenshots anpssen nach `<kundenname>/screenshots/<thema>/*.png` sortieren
4. Befehl ausführen

Dann im Chat: *"Baue das Schulungshandbuch für \<kundenname\>. Den Styleguide kannst du aus (website link / scss files / figma link)"* — der Skill übernimmt den Rest.

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
```

`jungmut/` (falls vorhanden) ist ein zweites Test-Beispiel: gleicher
Content wie `f4t/`, aber Design-Tokens live von jungmut.com extrahiert —
zeigt, dass derselbe Content-Code mit komplett anderem Branding
funktioniert. Die Screenshots darin sind zu Testzwecken von F4T
wiederverwendet (nicht echte Jungmut-Screenshots) — vor echter Auslieferung
durch reale Screenshots ersetzen.

## Warum kein Skill-Code in diesem Repo?

Den Skill findest Du in der ZIP im Repo