# handbuch-template

Vorlage für das **JUNGMUT WordPress-Redaktionshandbuch**. Das Handbuch besteht aus

1. **`basic.pdf`** – der fertigen Basis (39 Seiten, Kapitel 1–9): alles, was in
   jeder WordPress-Installation gleich ist – Login & Dashboard, Mediathek,
   Benutzer, Menüs, Gutenberg, Elementor, Do's & Don'ts, Blog, Custom Post Types,
   WPForms. Wird **nicht** neu generiert.
2. **Kunden-Erweiterung** – was nur dieser Kunde hat. Ihr schreibt Stichpunkte in
   `customer.md`, legt Screenshots in `assets/`, und der Skill
   `client-training-pdf` generiert daraus nur die zusätzlichen Kapitel (ab 10),
   hängt sie an die Basis an und erweitert das Inhaltsverzeichnis.

Das Ergebnis ist **immer im JUNGMUT-Design** – auch die neuen Seiten. Es wird
nichts an Kundenfarben oder -schriften angepasst.

```
handbuch-template/
├── README.md       ← diese Datei
├── basic.pdf       ← Basis-Handbuch (nicht bearbeiten)
├── basic.json      ← Kapitelliste der basic.pdf für den Skill (nicht bearbeiten)
├── customer.md     ← EURE Kunden-Ergänzungen
├── assets/         ← EURE Screenshots (Unterordner erlaubt)
├── skill.zip       ← der Claude-Skill client-training-pdf
├── build/          ← Zwischendateien vom Skill (gitignored)
└── output/         ← fertiges PDF: <Kunde>_Handbuch.pdf
```

## Skill einrichten (einmalig)

**Claude App / Cowork**
1. Claude App öffnen → Einstellungen → Skills → Hinzufügen → Skill hochladen
2. `skill.zip` aus diesem Repo hochladen (eine ältere Version vorher ersetzen)

**Claude Code (CLI)**
```bash
unzip skill.zip -d ~/.claude/skills/
```

## Neues Kundenhandbuch erstellen

1. Template für den Kunden kopieren bzw. forken:
   ```bash
   git clone <template-url> handbuch-<kunde>
   ```
2. `customer.md` ausfüllen (Beispielinhalte ersetzen) – siehe Guide unten.
3. Screenshots nach `assets/` legen, gerne in Unterordnern pro Thema
   (`assets/veranstaltungen/uebersicht.png`).
4. In Claude (Ordner verbunden bzw. im Repo gestartet) sagen:
   > *„Erstelle das Handbuch mit den Kunden-Erweiterungen."*
5. Ergebnis: `output/<Kunde>_Handbuch.pdf` – Cover mit „Schulungsunterlage ·
   &lt;Kunde&gt;", erweitertes Inhaltsverzeichnis, Basis-Kapitel 1–9, danach eure
   Kapitel mit durchlaufender Seitenzahl.

**Später ändern:** `customer.md` / `assets/` anpassen und wieder sagen
„Handbuch neu bauen". Die Basis wird dabei nie neu generiert – es kostet nur
die Kundenkapitel.

---

## Guide: customer.md richtig aufbereiten

### Die Grundregel: nur das Kundenspezifische

Alles aus der Basis (Kapitel 1–9) wird **nicht** wiederholt. Schreibt nur auf,
was bei diesem Kunden **zusätzlich oder anders** ist – z. B. eigene Post Types,
Spezial-Widgets, Mitgliederbereich, Shop, Mehrsprachigkeit, Workflows,
Ansprechpartner. Wenn etwas auf der Basis aufbaut, reicht ein Hinweis
(„Grundlagen siehe Kapitel 8") – Claude verweist dann darauf.

**Faustregel:** Würde der Satz bei jedem anderen WordPress-Kunden genauso
stimmen? → Steht schon in der Basis, weglassen.

### 1. Frontmatter (ganz oben)

```yaml
---
kunde: Musterkunde GmbH      # Pflicht – erscheint auf dem Cover und im Dateinamen
website: https://www.musterkunde.de   # optional, nur als Kontext
anrede: ihr                  # ihr (Standard) | du | Sie
---
```

### 2. Kapitel und Abschnitte

```markdown
# Veranstaltungen verwalten            ← neues Kapitel (bekommt automatisch Nr. 10, 11 …)
## Neue Veranstaltung anlegen          ← Abschnitt innerhalb des Kapitels
## Veranstaltungen importieren {toc}   ← eigenes Unterkapitel (10.1) mit Eintrag im Inhaltsverzeichnis
### Sonderfall Serientermine           ← kleinere Zwischenüberschrift
```
- Ein `#`-Kapitel pro größerem Thema/Bereich im Backend.
- `{toc}` nur für wirklich eigenständige Themen – das Inhaltsverzeichnis muss
  auf eine Seite passen (ca. 12–15 Kundeneinträge sind gut machbar).
- Keine Nummern selbst vergeben – macht der Skill.

### 3. Fakten vs. `AUSBAU:`

| Ihr schreibt …                                     | Claude macht …                                        |
|----------------------------------------------------|-------------------------------------------------------|
| normalen Text / Listen                             | übernimmt es inhaltlich 1:1, glättet nur die Sprache  |
| `AUSBAU: Stichpunkt`                               | formuliert 1–2 verständliche Absätze daraus           |
| `AUSBAU (kurz): …`                                 | 2–4 Sätze                                             |
| `AUSBAU (ausführlich): …`                          | mehrere Absätze, ggf. Schritte und Hinweisboxen       |

Gute `AUSBAU:`-Zeilen enthalten **die Fakten**, Claude liefert nur die
Formulierung:

```markdown
✗  AUSBAU: Mitgliederbereich erklären
✓  AUSBAU: Geschützter Bereich nur für eingeloggte Mitglieder. Mitglieder registrieren
   sich selbst, Redaktion schaltet unter Benutzer → „Ausstehend" frei. Rolle immer
   „Mitglied", nie „Redakteur".
```
Alles, was Claude nicht aus customer.md oder den Screenshots ablesen kann
(Menüpfade, Feldnamen, Regeln), muss drinstehen – sonst wird es weggelassen oder
nachgefragt, nicht erfunden.

### 4. Schritte

Nummerierte Listen werden zu Schritt-für-Schritt-Anleitungen. Menüpunkte und
Buttons **fett**, Pfade mit Pfeil:

```markdown
1. Im Hauptmenü auf **Veranstaltungen → Neu hinzufügen** klicken.
2. Titel eintragen und die Felder ausfüllen.
3. Rechts auf **Veröffentlichen** klicken.
```

### 5. Screenshots

```markdown
![Übersicht aller Veranstaltungen im Backend](veranstaltungen/uebersicht.png)
![Seitenleiste](menue/sidebar.png){schmal}
![Vorher](elementor/vorher.png) ![Nachher](elementor/nachher.png)
```
- Pfad ist **relativ zu `assets/`**.
- Der Text in `[ ]` wird zur Bildunterschrift – kurz und beschreibend.
- Zwei Bilder **in derselben Zeile** → nebeneinander.
- Optionale Breite: `{schmal}` (hochkante Ausschnitte), `{mittel}`, `{voll}`.
- Bild direkt **nach** dem Schritt platzieren, den es zeigt.
- Dateinamen sprechend, ohne Leerzeichen (`neue-veranstaltung-felder.png`).
- Screenshots in normaler Auflösung (Retina ist ok, wird automatisch verkleinert);
  vorher auf den relevanten Bereich zuschneiden, keine sensiblen Daten zeigen.

### 6. Hinweisboxen

```markdown
> **Tipp:** Nach der Rolle „Ausstehend" filtern zeigt alle offenen Anfragen.
> **Wichtig:** Vergangene Termine nicht löschen, sondern archivieren.
> **Gut zu wissen:** Termine erscheinen automatisch auf der Startseite.
```
„Wichtig" nur für Dinge, die beim Falschmachen wirklich etwas kaputt machen.

### 7. Feldübersichten (z. B. Custom Post Types, ACF)

```markdown
FELDER: Felder einer Veranstaltung
- Titel* : Name der Veranstaltung, erscheint als Überschrift
- Datum* : Startdatum, bei mehrtägigen Events zusätzlich „Enddatum"
- Ort : Freitext
```
`*` = Pflichtfeld (wird im PDF mit rotem Sternchen + Legende markiert).

### 8. Do's & Don'ts (kundenspezifisch)

```markdown
| Bereich  | Do                                  | Don't                         |
|----------|-------------------------------------|-------------------------------|
| Termine  | Vergangene Termine archivieren      | Termine löschen               |
```

### 9. Notizen an Claude

```markdown
<!-- Hinweis an Claude: Benutzerrollen stehen in Kapitel 2 – nur darauf verweisen. -->
```
Erscheinen nicht im PDF.

### Checkliste vor dem Bauen

- [ ] `kunde:` im Frontmatter gesetzt
- [ ] Beispielkapitel aus dem Template entfernt
- [ ] Nichts doppelt zur Basis (Kapitel 1–9)
- [ ] Jede `AUSBAU:`-Zeile enthält die nötigen Fakten
- [ ] Alle referenzierten Bilder liegen unter genau diesem Pfad in `assets/`
- [ ] Keine Zugangsdaten/Passwörter in Text oder Screenshots

---

## Basis aktualisieren

Wenn sich die `basic.pdf` ändert (neue Kapitel, andere Seitenzahlen):
neue `basic.pdf` hier ablegen und in `basic.json` die Kapitel mit Seitenzahl
sowie `pages` anpassen. Das Design der Basis und der Erweiterung kommt aus
derselben Datei (`scripts/jungmut.css` im Skill) – bei Design-Änderungen
beides zusammen aktualisieren.
