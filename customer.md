---
kunde: Musterkunde GmbH
website: https://www.musterkunde.de
anrede: ihr            # ihr | du | Sie  (Standard: ihr – wie in der basic.pdf)
---

<!--
  KUNDEN-ERGÄNZUNGEN ZUM WORDPRESS-HANDBUCH
  Alles, was in der basic.pdf schon steht (Login, Dashboard, Mediathek,
  Benutzer, Menüs, Gutenberg, Elementor, Do's & Don'ts, Blog, CPT-Grundlagen,
  WPForms), hier NICHT wiederholen – nur, was bei diesem Kunden anders oder
  zusätzlich ist. Ausführlicher Guide: README.md → "Guide: customer.md richtig aufbereiten".

  Kurzreferenz:
    # Titel                 → neues Kapitel (Nummer 10, 11, … wird automatisch vergeben)
    ## Titel                → Abschnitt im Kapitel
    ## Titel {toc}          → Unterkapitel mit eigener Seite + Eintrag im Inhaltsverzeichnis (10.1 …)
    AUSBAU: …               → Claude formuliert das aus  (auch: AUSBAU (kurz): / AUSBAU (ausführlich):)
    normaler Text           → wird inhaltlich 1:1 übernommen (nur sprachlich geglättet)
    ![Bildunterschrift](ordner/datei.png)        → Bild aus assets/
    ![A](a.png) ![B](b.png)                       → zwei Bilder nebeneinander (gleiche Zeile)
    ![Caption](datei.png){schmal|mittel|voll}     → Breite erzwingen (optional)
    > **Tipp:** …  /  > **Wichtig:** …  /  > **Gut zu wissen:** …   → Hinweisboxen
    FELDER: Titel  + Liste "- Feldname* : Beschreibung"  → Feldbox (* = Pflichtfeld)
    <!-- … -->              → Notiz an Claude, erscheint nicht im PDF
  Die Beispielkapitel unten ersetzen bzw. löschen.
-->

# Veranstaltungen verwalten

AUSBAU: Wofür der Bereich „Veranstaltungen" da ist – Termine erscheinen automatisch im Kalender auf /events und auf der Startseite (nächste 3 Termine).

![Übersicht aller Veranstaltungen im Backend](veranstaltungen/uebersicht.png)

## Neue Veranstaltung anlegen

1. Im Hauptmenü auf **Veranstaltungen → Neu hinzufügen** klicken.
2. Titel eintragen und die Felder unten ausfüllen.
3. Rechts auf **Veröffentlichen** klicken.

FELDER: Felder einer Veranstaltung
- Titel* : Name der Veranstaltung, erscheint als Überschrift
- Datum* : Startdatum, bei mehrtägigen Events zusätzlich „Enddatum"
- Ort : Freitext, z. B. „Köln, Mediapark 6"
- Anmeldelink : externer Link zur Anmeldung, optional

> **Wichtig:** Vergangene Veranstaltungen nicht löschen, sondern auf „Archiviert" setzen – sie werden sonst auch aus dem Rückblick entfernt.

AUSBAU (kurz): Unterschied zwischen „Entwurf", „Veröffentlicht" und „Archiviert" bei Veranstaltungen.

# Mitgliederbereich

AUSBAU (ausführlich): Geschützter Bereich nur für eingeloggte Mitglieder. Mitglieder registrieren sich selbst, die Redaktion schaltet sie unter Benutzer → „Ausstehend" frei. Rolle immer „Mitglied", nie „Redakteur".

![Seitenleiste mit dem Menüpunkt Mitglieder](veranstaltungen/sidebar.png){schmal}

## Mitglieder freischalten {toc}

AUSBAU: Schritt-für-Schritt Freischaltung, Bestätigungsmail geht automatisch raus.

> **Tipp:** Unter Benutzer lässt sich nach der Rolle „Ausstehend" filtern – so seht ihr sofort alle offenen Anfragen.

<!-- Hinweis an Claude: Benutzerrollen allgemein sind in Kapitel 2 der Basis erklärt – darauf verweisen, nicht wiederholen. -->
