# Briefing

## Sinn und Zweck

In diesem Wissensprojekt werden Ergebnisse aus Wissensarbeit erstellt. Quellen, Arbeitsstände und fertige Ergebnisse werden strikt voneinander getrennt.

Maximen:

1. **Quellen werden niemals verändert.**
2. **Fertige Ergebnisse sind eigenständig verständlich und nutzbar.**
3. **Belegte Aussagen, Interpretationen, Annahmen und Entscheidungen werden unterscheidbar dokumentiert.**
4. **Der aktuelle Arbeitsstand bleibt jederzeit wiederaufnehmbar.**

Die Arbeit soll pausiert und später fortgesetzt werden können, ohne relevantes Wissen, Entscheidungen oder offene Punkte zu verlieren.

---

## Priorität von Anweisungen

Bei Widersprüchen gilt folgende Reihenfolge:

1. Übergeordnete System-, Sicherheits- und Plattformvorgaben
2. Explizite aktuelle Benutzeranweisung
3. Unveränderlichkeit der Dateien unter `01_sources/`
4. Dieses Briefing
5. Weiterhin gültige Entscheidungen in `02_work/state.md`
6. Bestehende Inhalte unter `02_work/`
7. Selbstständige Annahmen des Agenten

Eine neue Benutzeranweisung darf frühere Entscheidungen ersetzen. Die Änderung wird in `state.md` unter `Decisions` dokumentiert.

---

## Verzeichnisstruktur

```text
01_sources/
02_work/
02_work/history/
02_work/archive/
02_work/assets/
02_work/build/
03_dist/
03_dist/assets/
```

### `01_sources/`

Enthält unveränderte Primärquellen.

Dateien unter `01_sources/` dürfen niemals:

* bearbeitet,
* überschrieben,
* umbenannt,
* verschoben,
* gelöscht

werden.

Neue Dateien dürfen nur dann unter `01_sources/` abgelegt werden, wenn der Benutzer dies ausdrücklich verlangt oder eine Datei ausdrücklich als Projektquelle bereitstellt.

### `02_work/`

Enthält interne Arbeitsstände:

* Analysen,
* Extraktionen,
* Verdichtungen,
* Entwürfe,
* Varianten,
* Hypothesen,
* Zwischenstände,
* temporäre Hilfsdateien,
* bearbeitbare Ausgangsdateien,
* Quellenindex und Arbeitszustand.

Dateien in `02_work/` dürfen aktualisiert, umstrukturiert, zusammengeführt und bereinigt werden. Dabei dürfen relevante Begründungen, Gegenpositionen, Unsicherheiten und offene Fragen nicht verloren gehen.

Dateien werden nicht automatisch gelöscht. Nicht mehr aktive Arbeitsstände können nach `02_work/archive/` verschoben werden.

### `03_dist/`

Enthält distributionsfähige Ergebnisse:

* freigabefähige Dokumente,
* Präsentationen,
* Websites,
* Konzepte,
* Prompts,
* Berichte,
* andere eigenständig nutzbare Artefakte.

Ein Ergebnis unter `03_dist/` muss ohne Zugriff auf `01_sources/` und `02_work/` verständlich und nutzbar sein.

Erforderliche Quellenangaben bleiben Bestandteil des Ergebnisses. Öffentliche und zugängliche Referenzen sind lokalen Projektpfaden vorzuziehen.

Bearbeitbare Arbeitsdateien verbleiben grundsätzlich unter `02_work/`. Distributionsfähige Ergebnisse werden nach `03_dist/` **kopiert**, nicht verschoben. Dies verhindert gebrochene Links und erhält den Arbeitskontext.

---

## Quellenklassen

### Primärquellen

Unveränderte Dateien unter:

```text
01_sources/
```

### Benutzerangaben

Informationen, die der Benutzer im Gespräch mitteilt.

Sie dürfen als Quelle verwendet werden, müssen aber als Benutzerangabe erkennbar bleiben.

Beispiel:

```markdown
Quelle: Benutzerangabe vom 2026-07-22
```

### Externe Quellen

Öffentliche Websites, Dokumentationen, Studien oder andere recherchierte Inhalte.

Externe Recherche erfolgt nur:

* auf ausdrückliche Anweisung des Benutzers,
* wenn sie für den Auftrag eindeutig erforderlich ist,
* oder wenn übergeordnete Vorgaben eine aktuelle Verifikation verlangen.

Neue externe Quellen werden nicht automatisch unter `01_sources/` gespeichert.

Sie werden zunächst dokumentiert in:

```text
02_work/source-candidates.md
```

Der Eintrag enthält mindestens:

* Titel,
* URL,
* Herausgeber oder Autor, sofern bekannt,
* Veröffentlichungsdatum, sofern bekannt,
* Abrufdatum,
* kurze Relevanzbewertung.

### Agentenableitungen

Zusammenfassungen, Interpretationen und Schlussfolgerungen des Agenten sind keine Quellen.

Sie müssen auf Quellen oder ausdrücklich gekennzeichneten Annahmen basieren.

---

## Quellenreferenzen

Arbeitsdateien unter `02_work/` müssen verwendete Quellen nachvollziehbar referenzieren.

### Lokale Dateien

```markdown
Quelle: [Dateiname](../01_sources/dateiname.pdf), S. 12–14
```

Bei Quellen ohne Seitenzahlen:

```markdown
Quelle: [Dateiname](../01_sources/dateiname.md), Abschnitt „Bezeichnung“
```

Falls keine präzisere Fundstelle möglich ist:

```markdown
Quelle: [Dateiname](../01_sources/dateiname.ext)
```

### Webquellen

```markdown
Quelle: Titel, URL, veröffentlicht am YYYY-MM-DD, abgerufen am YYYY-MM-DD
```

Nicht vorhandene Angaben werden weggelassen und nicht erfunden.

### Benutzerangaben

```markdown
Quelle: Benutzerangabe vom YYYY-MM-DD
```

### Ableitungen

```markdown
Ableitung aus:

- Quelle A, S. 4
- Quelle B, Abschnitt „Bezeichnung“
```

Direkte Zitate werden als Zitate gekennzeichnet. Übersetzungen eines Zitats werden als Übersetzung kenntlich gemacht.

---

## Trennung von Aussagearten

Arbeitsdateien müssen klar zwischen folgenden Aussagearten unterscheiden:

### Belegt

Direkt aus einer Quelle ableitbare oder durch mehrere Quellen gestützte Aussagen.

### Interpretation

Plausible Deutung belegter Informationen.

### Annahme

Noch nicht belegte Voraussetzung oder Arbeitshypothese.

### Entscheidung

Bewusst gewählte Festlegung für das weitere Vorgehen.

### Offene Frage

Noch nicht ausreichend beantwortete fachliche oder organisatorische Frage.

### Widerspruch

Nicht gleichzeitig vereinbare Aussagen oder Anforderungen.

Bei umfangreichen Arbeitsdateien soll folgende Struktur verwendet werden:

```markdown
## Belegte Erkenntnisse

## Interpretationen

## Annahmen

## Entscheidungen

## Offene Fragen

## Widersprüche und Risiken
```

Nicht jede Datei muss alle Abschnitte enthalten. Nicht belegte Aussagen dürfen jedoch nicht als gesicherte Fakten formuliert werden.

---

## Verlinkung von Arbeitsdateien

Verknüpfungen erfolgen über relative Markdown-Links.

Jede Arbeitsdatei verlinkt, soweit relevant:

* ihre Primärquellen,
* verwendete externe Quellen,
* verwandte Arbeitsdateien,
* daraus entstandene Ergebnisse unter `03_dist/`.

Inhalte sollen nicht unnötig dupliziert werden. Stattdessen werden kanonische Inhalte an einer Stelle gepflegt und von anderen Dateien aus verlinkt.

Wiki-spezifische Syntax oder proprietäre Linkformate werden nicht vorausgesetzt.

---

## Dateinamenskonventionen

Dateinamen werden:

* kleingeschrieben,
* aussagekräftig,
* mit Bindestrichen getrennt,
* ohne Begriffe wie `final`, `neu`, `wirklich-final` oder fortlaufende Versionszusätze angelegt.

Beispiele:

```text
02_work/zielgruppenanalyse.md
02_work/zielgruppenanalyse-alternativen.md
02_work/quellenbewertung-ki-brownfield.md
03_dist/positionierungskonzept-2026-07-22.md
```

Der aktuelle Stand einer Arbeitsdatei wird grundsätzlich in derselben Datei gepflegt.

Varianten werden nur dann getrennt, wenn sie bewusst parallel bestehen sollen.

---

## Quellenindex

Der Quellenstand wird gepflegt in:

```text
02_work/source-index.md
```

Empfohlene Struktur:

```markdown
# Source Index

Updated: YYYY-MM-DD HH:MM

| Quelle | Typ | Stand | Letzte Prüfung | Verwendet in | Hinweise |
|---|---|---|---|---|---|
| 01_sources/beispiel.pdf | Primärquelle | Hash oder Änderungsdatum | YYYY-MM-DD | 02_work/analyse.md |  |
```

Soweit technisch möglich, wird für lokale Quellen ein Hash verwendet. Andernfalls werden Dateigröße und Änderungsdatum dokumentiert.

Der Index dient dazu:

* neue Quellen zu erkennen,
* veränderte Quellen zu erkennen,
* Verwendungen nachzuvollziehen,
* nicht ausgewertete Quellen sichtbar zu machen.

Der Quellenindex ist kein Ersatz für präzise Referenzen innerhalb der Arbeitsdateien.

---

## Sprache

Outputs werden auf Deutsch verfasst, sofern nicht anders verlangt.

Englischsprachige Fachbegriffe, Eigennamen und Zitate können im Original übernommen werden, wenn dies präziser oder im Fachkontext üblich ist.

Übersetzte Zitate werden als Übersetzung gekennzeichnet.

---

## Arbeitszustand

Der aktuelle Zustand wird gepflegt in:

```text
02_work/state.md
```

`state.md` ist kein chronologisches Protokoll. Die Datei enthält ausschließlich den aktuell relevanten Stand.

Sie wird automatisch aktualisiert:

* nach wesentlichen inhaltlichen Änderungen,
* nach relevanten Entscheidungen,
* nach dem Erstellen oder Überarbeiten eines zentralen Artefakts,
* nach dem Auftreten eines neuen Widerspruchs oder Risikos,
* bei `project update`,
* bei `project close`,
* wenn der Benutzer dies verlangt.

Keine Aktualisierung ist nötig bei:

* rein lesenden Tätigkeiten,
* kleinen Formulierungsänderungen,
* folgenlosen Formatkorrekturen,
* unveränderten Rechercheergebnissen.

Eine Änderung ist wesentlich, wenn sie das Ziel, den Wissensstand, eine Entscheidung, einen offenen Punkt, ein Risiko, eine nächste Aktion oder eine aktive Datei verändert.

Struktur:

```markdown
# State

Updated: YYYY-MM-DD HH:MM

## Current Goal

Das aktuell verfolgte Ziel.

## Current State

Kurze Beschreibung des erreichten Stands.

## Last Work

Was zuletzt konkret bearbeitet wurde.

## Decisions

- Getroffene und weiterhin relevante Entscheidungen

## Open Questions

- Noch nicht beantwortete Fragen

## Next Actions

- Sinnvolle nächste Schritte in Prioritätsreihenfolge

## Active Files

- 02_work/name1.md
- 02_work/name2.md

## Risks and Conflicts

- Bekannte Widersprüche, Unsicherheiten oder Risiken
```

Überholte Entscheidungen werden nicht kommentarlos entfernt. Sie werden durch die aktuell gültige Entscheidung ersetzt. Falls der Entscheidungswechsel später relevant sein kann, wird er zusätzlich in der Historie dokumentiert.

---

## Historie

Es werden keine Sitzungsprotokolle für jede Interaktion erstellt.

Bei jedem `project close` wird jedoch ein kompakter History-Eintrag erzeugt:

```text
02_work/history/YYYY-MM-DD-HHMM.md
```

Die Historie ist append-only:

* bestehende History-Dateien werden nicht verändert,
* frühere Einträge werden nicht gelöscht,
* Korrekturen erfolgen durch einen neuen Eintrag.

Struktur:

```markdown
# Project Close — YYYY-MM-DD HH:MM

## Goal

## Completed

## Decisions

## Open Questions

## Next Actions

## Changed Files

## Risks and Conflicts
```

Die Historie hält nur wesentliche Änderungen fest. Sie ist kein vollständiges Gesprächsprotokoll.

---

## Assets und Binärformate

Verwende:

```text
02_work/assets/
```

für bearbeitete Bilder, Diagramme und andere interne Medien.

Verwende:

```text
02_work/build/
```

für:

* temporäre Exporte,
* Build-Dateien,
* Render-Zwischenstände,
* generierte Hilfsdateien.

Verwende:

```text
03_dist/assets/
```

für Medien, die Bestandteil eines distributionsfähigen Ergebnisses sind.

Bearbeitbare Quelldateien verbleiben unter `02_work/`. Exportierte Endformate werden nach `03_dist/` kopiert.

Temporäre Build-Dateien dürfen bereinigt werden, wenn sie reproduzierbar und nicht mehr erforderlich sind. Primärquellen und relevante Arbeitsstände dürfen dabei nicht gelöscht werden.

---

## Widersprüche

Bei einem Widerspruch:

1. Verändere keine Aussage stillschweigend.
2. Dokumentiere beide Positionen.
3. Ermittle Herkunft, Kontext und Evidenz.
4. Prüfe, ob eine Aussage:

   * veraltet,
   * kontextabhängig,
   * unvollständig,
   * schwächer belegt
     ist.
5. Löse den Widerspruch selbstständig, wenn Evidenz und Prioritätsregeln eindeutig sind.
6. Dokumentiere die Lösung und ihre Begründung.
7. Lege dem Benutzer die konkrete Entscheidung vor, wenn eine fachliche oder geschäftliche Bewertung notwendig bleibt.

Ein ungelöster Widerspruch wird unter folgenden Stellen festgehalten:

* in der betroffenen Arbeitsdatei,
* in `02_work/state.md` unter `Risks and Conflicts`,
* gegebenenfalls unter `Open Questions`.

---

## Umgang mit Unsicherheit

Fehlende Informationen werden nicht erfunden.

Kann eine Aufgabe trotz einer Unsicherheit sinnvoll fortgeführt werden, verwendet der Agent eine ausdrücklich gekennzeichnete Arbeitsannahme.

Beispiel:

```markdown
Annahme: Für die weitere Analyse wird zunächst davon ausgegangen, dass …
```

Eine Benutzerentscheidung ist nur erforderlich, wenn:

* mehrere plausible Optionen zu wesentlich verschiedenen Ergebnissen führen,
* geschäftliche, fachliche oder normative Bewertung notwendig ist,
* eine irreversible Aktion betroffen ist,
* ein distributionsfähiges Ergebnis sonst irreführend wäre.

Kleine oder leicht reversible Entscheidungen trifft der Agent selbstständig und dokumentiert sie.

---

## Artefakte und Reifegrad

Ein Ergebnis ist distributionsreif, wenn es:

* den aktuellen Auftrag vollständig erfüllt,
* ohne interne Arbeitsnotizen verständlich ist,
* keine ungeklärten Platzhalter enthält,
* keine als Fakten formulierten unbelegten Annahmen enthält,
* notwendige Quellenangaben enthält,
* sprachlich und strukturell geprüft wurde,
* im vorgesehenen Zielformat nutzbar ist.

Ist der Reifegrad eindeutig, schlägt der Agent vor, das Ergebnis nach `03_dist/` zu kopieren.

Vor dem Kopieren ist die ausdrückliche Zustimmung des Benutzers erforderlich.

Ohne Zustimmung:

* verbleibt das Ergebnis unter `02_work/`,
* wird keine Datei unter `03_dist/` erstellt oder überschrieben,
* wird die mögliche Distribution unter `Next Actions` in `state.md` festgehalten.

Ist der Reifegrad unklar, bleibt das Ergebnis unter `02_work/` und wird als offener Punkt dokumentiert.

Bearbeitbare Arbeitsdateien werden niemals automatisch nach `03_dist/` verschoben.

Bestehende Dateien unter `03_dist/` werden nicht ohne ausdrückliche Zustimmung überschrieben. Bei einer Aktualisierung schlägt der Agent eine der folgenden Varianten vor:

* bestehende Datei ersetzen,
* datierte neue Version erzeugen.

Die gewählte Variante wird dokumentiert.

---

# User Commands

Die folgenden Commands sind semantische Befehle. Der Benutzer muss sie nicht exakt schreiben. Gleichbedeutende natürliche Formulierungen sind ebenfalls gültig.

## `project status`

Beispiele:

```text
project status
Wo stehen wir?
Was ist hier der aktuelle Stand?
```

Ablauf:

1. Lies `02_work/state.md`.
2. Prüfe die unter `Active Files` genannten Dateien.
3. Prüfe relevante Einträge im Quellenindex.
4. Lies weitere Dateien nur:

   * wenn `state.md` fehlt,
   * wenn der Zustand widersprüchlich wirkt,
   * wenn aktive Dateien fehlen,
   * oder wenn die Benutzerfrage mehr Details erfordert.
5. Fasse zusammen:

   * Ziel,
   * aktuellen Stand,
   * letzte Ergebnisse,
   * offene Fragen,
   * nächste Aktionen,
   * relevante Risiken.
6. Verändere keine Dateien, außer der Benutzer bittet ausdrücklich um eine Aktualisierung.

Wenn `state.md` offensichtlich veraltet ist, weise darauf hin, ohne sie automatisch zu verändern.

---

## `project update`

Beispiele:

```text
project update
Aktualisiere den Workspace.
Aktualisiere work.
Prüfe, ob es neues relevantes Wissen gibt.
```

Ablauf:

1. Lies `state.md` und `source-index.md`.
2. Prüfe vorhandene Quellen unter `01_sources/` auf:

   * neue Dateien,
   * veränderte Dateien,
   * bisher nicht ausgewertete Dateien.
3. Aktualisiere `source-index.md`.
4. Prüfe bestehende Quellenreferenzen.
5. Werte neues oder verändertes Wissen aus.
6. Externe Recherche erfolgt nur nach den Regeln unter `Externe Quellen`.
7. Ergänze, korrigiere oder entferne überholte Inhalte und Verweise unter `02_work/`.
8. Dateien unter `01_sources/` werden niemals verändert oder gelöscht.
9. Vergleiche neues Wissen mit:

   * aktuellen Annahmen,
   * Entscheidungen,
   * Erkenntnissen,
   * offenen Fragen,
   * bestehenden Artefakten.
10. Markiere:

    * neue Erkenntnisse,
    * veraltete Aussagen,
    * Widersprüche,
    * mögliche Auswirkungen.
11. Aktualisiere `state.md`.
12. Verändere distributionsfähige Artefakte nur:

    * wenn der Benutzer dies verlangt,
    * oder wenn ihre Aktualisierung eindeutig Teil des Auftrags ist.
13. Berichte knapp:

    * was sich geändert hat,
    * welche Auswirkungen bestehen,
    * welche Fragen offen bleiben.

---

## `project close`

Beispiele:

```text
project close
Projekt schließen.
Für heute reicht es.
Halte den Stand fest.
```

Ablauf:

1. Lies `state.md`, aktive Dateien und relevante Quellenreferenzen.
2. Ermittle alle seit dem letzten History-Eintrag relevanten Änderungen.
3. Prüfe, ob unfertige Arbeitsstände existieren.
4. Prüfe, ob Entscheidungen, Annahmen, offene Fragen und Risiken korrekt dokumentiert sind.
5. Aktualisiere `state.md` vollständig.
6. Halte insbesondere fest:

   * aktuelles Ziel,
   * erreichten Stand,
   * zuletzt bearbeitete Inhalte,
   * weiterhin gültige Entscheidungen,
   * offene Fragen,
   * nächste sinnvolle Schritte,
   * aktive Dateien,
   * Risiken und Widersprüche.
7. Erzeuge einen neuen History-Eintrag unter:

   ```text
   02_work/history/YYYY-MM-DD-HHMM.md
   ```
8. Prüfe, ob distributionsfähige Ergebnisse unter `02_work/` liegen.
9. Benenne eindeutig distributionsfähige Ergebnisse und schlage vor, sie nach `03_dist/` zu kopieren.
10. Kopiere oder überschreibe keine Datei ohne ausdrückliche Zustimmung des Benutzers.
11. Verschiebe keine Arbeitsdateien automatisch.
12. Bei unklarem Reifegrad:

    * keine Distribution vorschlagen,
    * offene Qualitäts- oder Inhaltsfragen in `state.md` dokumentieren.
13. Teile dem Benutzer knapp mit:

    * was festgehalten wurde,
    * welche Ergebnisse distributionsfähig erscheinen,
    * für welche Distribution eine Zustimmung benötigt wird,
    * welche offenen Punkte bestehen,
    * wo sinnvoll weitergearbeitet werden kann.


`project close` beendet das Thema nicht dauerhaft. Es erzeugt einen belastbaren Wiedereinstiegspunkt.
