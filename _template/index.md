# WordPress Schulung to PDF

# 1. WordPress Grundlagen
AUSBAU: WordPress Basics (login über "/wp-admin", Übersicht im Backend, Post Types, Einstellungen). Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.

![image](./references/dashboard/backend-uebersicht.png)
![image](./references/dashboard/login-form.png)
![image](./references/dashboard/wp-admin-url.png)


# 1.1 Mediathek 
AUSBAU: Mediathek erklärt (Alt-Texte, Title, Beschreibung, Beschriftung, Bild austauschen mit media replace plugin, Ansicht ändern, Lieber Bilder / Medien in der bestehenden Bibliothek suchen vor dem Hochladen um Duplikate zu vermeiden). Wie lade ich ein Bild hoch (select methode mit browser oder drag n drop)
![image](./references/mediathek/mediathek-overview.png)
![image](./references/mediathek/overview-list-ansicht.png)
![image](./references/mediathek/single-image-overlay%20(alt,%20description%20etc).png)


# 2. Benutzerverwaltung
AUSBAU: Ekläre Benutzerverwaltung. Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.
STICHPUNKTE 
  - Benutzer erstellen
  - Benutzer Verwalten
  - Rollen und Erklärungen (Welche Rechte, wo sind die Unterschieden)

![image](./references/user/user-roles-select.png)
![image](./references/user/user-wp-menu.png)
![image](./references/user/users-overview.png)


# 3. Menüverwaltung 
AUSBAU: Erkläre wie man Menüs erstellt und bearbeitet. Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.
STICHPUNKTE 
  - Menü erstellen
  - Menü Auswählen 
  - Menü Punkt bearbeiten (löschen, suchen, umbenennen)
  - Wichtig: Menü Design unterschützt nur 2 ebenen

![image](./references/menu/add-menu-widget.png)
![image](./references/menu/change-menu-select.png)
![image](./references/menu/menu-entry-design.png)
![image](./references/menu/menu-structure.png)
![image](./references/menu/overview-menus.png)


# 4. Seiten anlegen mit Gutenberg
AUSBAU: Erklärung vom Gutenberg Editor. Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.
STICHPUNKTE: 
  - Was ist ein Titel, Textauszug, Beitragsbild
  - Basics Blöcke 
  - Basic Blöcke einzeln kurz aufgelistet (headline, absatz, bild, video)
  - Suchfunktion der Blöcke benennen
  - Kategorien und Taxonomien zuweisen, erstellen, löschen
  - Statuse erklären und wo die unterschiede sind

![image](./references/gutenberg/add-blocks-layover.png)
![image](./references/gutenberg/blocks-big-overview.png)
![image](./references/gutenberg/gutenberg-overview-blank.png)
![image](./references/gutenberg/headline-block-settings.png)
![image](./references/gutenberg/image-block-settings.png)
![image](./references/gutenberg/kategorie-taxonomy-publish-sidebar-right.png)


# 5. Seiten anlegen mit Elementor 
AUSBAU: Wie baue ich Seiten mit Elementor auf. !ganz wichtig!: Wir raten davon ab selbst sections zu erstellen. Stattdessen haben wir für für jede Section die es auch im Styleguide gibt, ein Elementor Template angelegt im Folgenden soll beschrieben werden: 

STICHPUNKTE:
  - Wie erreiche ich die Template 
  - Wie füge ich das Template ein 
  - Wie bearbeite ich grundlegend den Inhalt eines Templates (Normale Elementor Section mit Widgets und Custom widgets. Das meiste finde im Bereich des Inhalts statt)
  - Wie greife ich auf die ebenen Ansicht (Struktur zu)
  - Kopieren zwischen Elementor Seiten 
  - Vorschau im Elementor Modus
  - Speichern / Veröffentlichen

Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.

![image](./references/elementor/blank-page-overview.png)
![image](./references/elementor/copy-context-menu-section.png)
![image](./references/elementor/edit-image-elementor-content.png)
![image](./references/elementor/edit-with-el-button.png)
![image](./references/elementor/el-templates-overview.png)
![image](./references/elementor/elementor-context-menu.png)
![image](./references/elementor/elementor-preview-or-publish-buttons.png)
![image](./references/elementor/elementor-structure-layers-view.png)
![image](./references/elementor/empty-el-section-add-template-trigger.png)
![image](./references/elementor/example-add-template-in-menu.png)
![image](./references/elementor/example-inserted-template-section.png)
![image](./references/elementor/paste-context-menu.png)
![image](./references/elementor/widgets-sidebar-basics.png)
![image](./references/elementor/widgets-sidebar-custom-widgets.png)



# 6. Dos and donts

| Bereich            | ✅ Do                                                                          | ❌ Don't                                                                               |
| ------------------ | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Layout & Abstände  | Bestehende Templates & Sections verwenden und Inhalte darin austauschen       | Abstände (Padding/Margin) frei per Hand einstellen – das Design-System bricht dadurch |
| Neue Seiteninhalte | Vorhandene Section kopieren und Inhalt anpassen ('Duplicate' statt neu bauen) | Neue Sections von Grund auf selbst zusammenbauen                                      |
| Schriften & Farben | Nur die vordefinierte Farb- und Schrift-Palette (Global Colors/Fonts) nutzen  | Eigene Farben/Schriftgrößen frei per Colorpicker wählen                               |
| Bilder             | Optimierte Bilder im empfohlenen Format & Seitenverhältnis hochladen          | Unkomprimierte Riesendateien direkt aus dem Handy hochladen                           |
| Struktur           | Neue Inhalte über Publikationen/Veranstaltungen (CPTs) anlegen                | ‘‘Neue Unterseiten wild anlegen, ohne Menüstruktur zu pflegen                         |
| Plugins            | Rückfrage bei der Agentur vor Installation neuer Plugins                      | Beliebige Plugins ohne Rücksprache installieren                                       |





# 7. Veranstaltung anlegen
AUSBAU: Wie legt man eine Veranstaltung an. Custom Post Type. "Optional" wird nicht angezeigt im Teaser, wenn es nicht vorhanden ist. Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.
Name: Events
Besonderheiten: 
- Inhalt = Beschreibung
- ACF Date Field für Datum (Pflicht)
- Location für Ortfeld (optional, wird sonst nicht angezeigt im teaser)
- ACF Feld Start => Anfangszeit (optional)
- ACF Feld Ende => Endzeit (optional)
- ACF Feld Event Link! => Ist für die Event Seite, auf die weitergeleitet wird, weil keine Event single pages. (Pflicht)
- Kategorien zuwesisen (optional aber empfohlen)

![image](./references/events/events-post-type-overview.png)


# 8. In den Medien anlegen
AUSBAU: Wie legt man einen Post zu "In den Medien" an. Custom Post Type. 
Name: In den Medien
Besonderheiten: 
- Inhalt = Gutenberg Umsetzung
- Zuweiseung Taxonomy Media Type



# 9. Pressemitteilungen anlegen
AUSBAU: Wie legt man einen Post zu "Pressemitteilung" an. Custom Post Type.
Name: Pressemitteilung
Besonderheiten: 
- Inhalt = Gutenberg Umsetzung


# 10. Blogbeitrag anlegen (Post)
AUSBAU: Wie legt man einen Post an. Custom Post Type. Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.
Name: Beitrag
Besonderheiten: 
- Inhalt = Gutenberg Umsetzung
- ACF Feld für Ansprechpartner. Post Type Team Verknüpfung, zeigt die Kontaktperson unten am Post an
- Zuweisung Kategorie für Filterung
- Beitragsbild festlegen 
- Taxonomien / Kategorien festlegen
- Besonderheit bei Kategorie Tax: Es gibt Farben, die man den Kategorien per Farbauswahl (color input und color swatches zum klicken) zuweisen kann, welcher dann in dem Teaser im Tag als Hintergrundfarbe angezeigt wird.


![image](./references/blog/blog-menu.png)
![image](./references/blog/blog-overview.png)
![image](./references/blog/gutenberg-overview.png)
![image](./references/blog/taxonomies-overview.png)


# 11. Team Member anlegen
AUSBAU: Wie legt man einen Post ""Team" an. Custom Post Type. Benutze das folgende Bildmaterial. Benennungen sind im Dateinamen.
Name: Team
Besonderheiten: 
- Inhalt = Beschreibungstext
- ACF Feld Position für Position im Teaser
- ACF Feld E-Mail für E-Mail adresse im Teaser
- ACF Feld LinkedIn Verlinkung 
- Beitragsbild festlegen (Profilbild für Kontaktperson) 
- ACF Felder vor und Nachname für Sortierung nach Nachname in der Übersicht


![image](./references/craete-team-overview.png)