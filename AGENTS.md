# Briefing

## Sinn und Zweck

In diesem Wissensprojekt werden Ergebnisse aus Wissensarbeit erstellt.

---

## Projektstart

Bevor die eigentliche Wissensarbeit beginnt, klärt der Agent gemeinsam mit dem Benutzer den Projektauftrag.

Ziel ist kein vollständiges Projektkonzept, sondern ein ausreichend klares gemeinsames Verständnis für den nächsten sinnvollen Arbeitsschritt.

Der Agent klärt insbesondere:

1. **Ziel**
   Was soll durch dieses Projekt erreicht, geklärt oder ermöglicht werden?

2. **Ergebnisse**
   Welche konkreten Ergebnisse könnten am Ende entstehen?

3. **Zielgruppe**
   Für wen sind die Ergebnisse bestimmt und wie sollen sie genutzt werden?

4. **Erfolg**
   Woran wäre erkennbar, dass das Projekt erfolgreich war?

5. **Kontext und Grenzen**
   Welche Rahmenbedingungen, Abhängigkeiten oder bewussten Nicht-Ziele gibt es?

6. **Ausgangslage**
   Welche Quellen, Vorarbeiten, Entscheidungen oder offenen Fragen existieren bereits?

7. **Startbereitschaft**
   Soll direkt mit vorhandenen Quellen gearbeitet werden, sollen zunächst weitere Quellen gesammelt werden oder soll zuerst der Projektauftrag geschärft werden?

Der Agent fragt nur nach Informationen, die für den aktuellen nächsten Schritt relevant sind. Unnötige Vorabplanung wird vermieden.

Auf Basis der Antworten schlägt der Agent eine schlanke initiale Arbeitsstruktur unter `02_work/` vor. Diese Struktur ist vorläufig und darf sich mit wachsendem Verständnis verändern.

Der initiale Projektstand wird so dokumentiert, dass jederzeit erkennbar ist:

* was das Projekt erreichen soll,
* welche Ergebnisse aktuell angestrebt werden,
* welche Quellen verfügbar und welche bereits ausgewählt sind,
* welche Annahmen und Entscheidungen gelten,
* woran aktuell gearbeitet wird,
* welche Fragen offen sind,
* was als Nächstes sinnvoll ist.

Der Agent macht anschließend einen konkreten Vorschlag für den nächsten Schritt und wartet auf Bestätigung, bevor Quellen ingestiert oder größere Arbeitsstrukturen angelegt werden.

Startdateien (Minimum):

```text
02_work/
├── project-brief.md
├── state.md
```

Mehr zu state.md siehe unten.

---

## Arbeitsweise

Quellen, Arbeitsstände und fertige Ergebnisse werden strikt voneinander getrennt.

Maximen:

1. **Quellen werden niemals verändert.**
2. **Quellen werden zuerst inventarisiert und erst nach Auswahl durch den Benutzer ingestiert.**
3. **Wissensarbeit entsteht zuerst unter `02_work/`; eine Distribution nach `03_dist/` erfolgt erst nach gemeinsamer Klärung.**
4. **Fertige Ergebnisse sind eigenständig verständlich und nutzbar.**
5. **Belegte Aussagen, Interpretationen, Annahmen und Entscheidungen werden unterscheidbar dokumentiert.**
6. **Der aktuelle Arbeitsstand bleibt jederzeit wiederaufnehmbar.**

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

Der Agent erstellt nicht unmittelbar nach Sichtung oder Ingestion von Quellen ein Ergebnis unter `03_dist/`. Vor jeder Distribution werden Wissen, offene Fragen, Widersprüche, Zielgruppe, Format und gewünschter Verwendungszweck gemeinsam mit dem Benutzer geklärt.

### `.template-version`

Enthält, sofern dieses Projekt aus dem öffentlichen Template [`agentic-project-template`](https://github.com/ag-constructiva/agentic-project-template) hervorgegangen ist, den zuletzt synchronisierten Stand dieses Templates.

Format:

```text
repo: https://github.com/ag-constructiva/agentic-project-template
commit: <commit-hash>
synced: YYYY-MM-DD
```

Diese Datei wird ausschließlich durch den Befehl `update agentic-project-template` angelegt oder aktualisiert. Sie ist kein Bestandteil der Wissensarbeit und wird nicht unter `01_sources/`, `02_work/` oder `03_dist/` abgelegt.

### `UPDATE.md`

Enthält das vollständige Ablaufprotokoll für den Befehl `update agentic-project-template`, ausschließlich für den Agenten bestimmt. Wird nur bei Ausführung dieses Befehls gelesen. Kein Bestandteil der Wissensarbeit; wird nicht unter `01_sources/`, `02_work/` oder `03_dist/` abgelegt. Menschenlesbare Nutzungsinfos zu diesem Befehl siehe `README.md`.

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

### Quellenglaubwürdigkeit

Der Benutzer kann jeder Quelle unabhängig von ihrer Klasse eine Glaubwürdigkeitseinstufung zuweisen: `LOW`, `MEDIUM`/`MED` oder `HIGH`.

Die Einstufung wird auf zwei Wegen erkannt:

1. **Dateiname**: Enthält der Dateiname einen der Begriffe `LOW`, `MEDIUM`, `MED` oder `HIGH` vollständig großgeschrieben als eigenständigen Bestandteil (z. B. getrennt durch `-`, `_` oder Leerzeichen), gilt dies als Einstufung durch den Benutzer.
   Beispiel: `interview-notizen-HIGH.md`
2. **Inhaltliche Annotation**: Findet sich in den ersten Zeilen einer Quelle ein erkennbarer Hinweis zur Glaubwürdigkeit (z. B. `Glaubwürdigkeit: MEDIUM` oder ein vergleichbarer Hinweis in Textform), gilt dies ebenfalls als Einstufung durch den Benutzer.

Eine inhaltliche Annotation hat immer Vorrang vor einer Einstufung über den Dateinamen.

Eine erkannte Glaubwürdigkeitseinstufung wird im Quellenindex (`02_work/source-index.md`) festgehalten und bei der Gewichtung von `Belegte Erkenntnisse` und `Interpretationen` berücksichtigt. Fehlt eine Einstufung, gilt die Quelle als nicht eingestuft; dies wird nicht mit `MEDIUM` gleichgesetzt.

#### Konsequenzen der Einstufung

* **HIGH**: Auf dieser Quelle beruhende Aussagen gelten als belegte Grundlage. Der Agent baut ohne weitere Rückfrage auf ihnen auf.
* **MEDIUM**: Auf dieser Quelle beruhende Aussagen sind grundsätzlich nutzbar. Der Agent weist an geeigneter Stelle darauf hin und schlägt dem Benutzer konkret vor, entweder weitere Quellen beizusteuern oder eine externe Recherche zur Bestätigung durchzuführen. Eine externe Recherche wird dabei nicht automatisch ausgeführt, sondern folgt weiterhin den Regeln unter `Externe Quellen` (nur nach ausdrücklicher Anweisung).
* **LOW**: Jedes Arbeitsergebnis unter `02_work/`, das auf dieser Quelle beruht, erhält an der jeweiligen Stelle einen sichtbaren Warnhinweis (z. B. „> Warnhinweis: Aussage beruht auf einer Quelle mit geringer Glaubwürdigkeit"). Zusätzlich wird eine offene Aufgabe dokumentiert, weitere Evidenz zu beschaffen — unter `Offene Fragen` in der betroffenen Arbeitsdatei sowie unter `Open Questions` bzw. `Next Actions` in `state.md`. Diese offene Aufgabe bleibt bestehen, bis der Benutzer ausdrücklich etwas anderes festlegt (z. B. dass die Quelle trotz geringer Glaubwürdigkeit als ausreichend akzeptiert wird).

Fehlt eine Einstufung, wird keine dieser Konsequenzen automatisch angewendet.

---

## Quellenaufnahme und Ingestion

Quellen werden nicht automatisch vollständig eingelesen, ausgewertet oder verdichtet. Die Quellenaufnahme erfolgt stufenweise.

### 1. Quelleninventar erstellen

Der Agent prüft zunächst ausschließlich, welche Quellen vorhanden sind. Dabei werden soweit technisch möglich erfasst:

* Dateiname oder Bezeichnung,
* Typ und Format,
* Größe, Änderungsdatum oder Hash,
* grober erkennbarer Gegenstand,
* möglicher Bezug zum aktuellen Ziel,
* aktueller Ingestion-Status.

Diese erste Prüfung dient der Orientierung. Sie ist noch keine vollständige inhaltliche Auswertung.

### 2. Ingestion vorschlagen und abstimmen

Auf Basis des Inventars schlägt der Agent vor:

* welche Quellen voraussichtlich relevant sind,
* in welcher Reihenfolge sie ingestiert werden sollten,
* welche Quellen zunächst zurückgestellt werden können,
* ob eine vollständige oder selektive Ingestion sinnvoll ist.

Vor der erstmaligen Ingestion einer Quelle ist die Auswahl mit dem Benutzer abzustimmen. Eine explizite aktuelle Benutzeranweisung kann die Ingestion unmittelbar freigeben.

### 3. Ingestion nachvollziehbar durchführen

Für jede Quelle wird im Quellenindex mindestens einer dieser Zustände gepflegt:

* `inventarisiert` — Quelle erkannt, aber noch nicht inhaltlich ausgewertet,
* `zur-ingestion-vorgeschlagen` — vom Agenten zur Auswertung empfohlen,
* `freigegeben` — vom Benutzer zur Ingestion ausgewählt,
* `teilweise-ingestiert` — nur relevante Teile wurden ausgewertet,
* `vollständig-ingestiert` — die Quelle wurde im erforderlichen Umfang vollständig ausgewertet,
* `zurückgestellt` — aktuell bewusst nicht auszuwerten,
* `nicht-relevant` — für das aktuelle Ziel nachweislich nicht erforderlich,
* `fehlerhaft` — Ingestion war technisch oder inhaltlich nicht möglich.

Bei teilweiser Ingestion wird dokumentiert, welche Seiten, Abschnitte, Bereiche oder Daten berücksichtigt wurden.

### 4. Wissen unter `02_work/` aufbereiten

Ingestierte Inhalte werden zunächst ausschließlich unter `02_work/` verarbeitet. Dort entstehen:

* Extraktionen und strukturierte Notizen,
* belegte Erkenntnisse,
* Interpretationen und Annahmen,
* Quellenvergleiche,
* offene Fragen,
* Widersprüche und Risiken,
* mögliche Zielbilder und Ergebnisvarianten.

Eine erste Verdichtung ist ein Arbeitsstand, kein distributionsfähiges Ergebnis.

### 5. Offene Punkte klären

Vor der Distribution prüft der Agent insbesondere:

* Welche relevanten Quellen sind noch nicht ingestiert?
* Welche Aussagen sind unklar, unbelegt oder widersprüchlich?
* Welche Entscheidungen benötigen fachliche oder geschäftliche Bewertung?
* Welche Zielgruppe, Nutzungssituation und Ergebnisform werden benötigt?
* Welche Inhalte müssen noch ergänzt, verworfen oder priorisiert werden?

Der Agent löst eindeutige Punkte selbstständig. Verbleibende Entscheidungen legt er dem Benutzer konkret und mit Vorschlag vor.

### 6. Distribution gemeinsam festlegen

Erst nach der Klärung schlägt der Agent konkrete Artefakte für `03_dist/` vor, beispielsweise:

* Ziel und Zweck des Ergebnisses,
* Zielgruppe,
* Format,
* Umfang und Struktur,
* Varianten oder Priorisierung,
* Dateiname und Zielformat.

Für Erstellung, Kopie oder Aktualisierung unter `03_dist/` gilt die Zustimmungspflicht aus `Artefakte und Reifegrad`.

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

| Quelle | Typ | Glaubwürdigkeit | Technischer Stand | Ingestion-Status | Ingestierter Umfang | Letzte Prüfung | Verwendet in | Hinweise |
|---|---|---|---|---|---|---|---|---|
| 01_sources/beispiel.pdf | Primärquelle | — | Hash oder Änderungsdatum | inventarisiert | — | YYYY-MM-DD | — |  |
```

Soweit technisch möglich, wird für lokale Quellen ein Hash verwendet. Andernfalls werden Dateigröße und Änderungsdatum dokumentiert.

Der Index dient dazu:

* neue Quellen zu erkennen,
* veränderte Quellen zu erkennen,
* den Ingestion-Status jeder Quelle nachzuvollziehen,
* den bereits ausgewerteten Umfang sichtbar zu machen,
* Verwendungen nachzuvollziehen,
* nicht ausgewertete oder zurückgestellte Quellen sichtbar zu machen.

Eine Quelle gilt nicht allein deshalb als ingestiert, weil sie technisch geöffnet, aufgelistet oder oberflächlich geprüft wurde.

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

Kurze Beschreibung des erreichten Stands einschließlich Quelleninventar und Ingestion-Fortschritt.

## Last Work

Was zuletzt konkret bearbeitet wurde.

## Decisions

- Aktuell gültige Entscheidungen mit Verweis auf den zugehörigen ADR unter `02_work/decisions.md`

## Open Questions

- Noch nicht beantwortete fachliche Fragen
- Noch offene Entscheidungen zur Quellen-Ingestion
- Noch offene Entscheidungen zu Zielgruppe, Format oder Distribution

## Next Actions

- Sinnvolle nächste Schritte in Prioritätsreihenfolge

## Active Files

- 02_work/name1.md
- 02_work/name2.md

## Risks and Conflicts

- Bekannte Widersprüche, Unsicherheiten oder Risiken
```

Überholte Entscheidungen werden nicht kommentarlos entfernt. Sie werden durch die aktuell gültige Entscheidung ersetzt und zu dem zugehörigen ADR referenziert. `state.md` enthält nur die gegenwärtig gültige Entscheidung; die dauerhafte Entscheidungshistorie liegt in `02_work/decisions.md`.

---

## Architecture Decision Records (ADR)

Dauerhafte Entscheidungen werden als append-only geführte ADRs dokumentiert unter:

```text
02_work/decisions.md
```

ADRs halten fest, warum eine Entscheidung getroffen wurde. Sie ersetzen weder den aktuellen Arbeitszustand in `state.md` noch die Arbeitsabschluss-Historie unter `02_work/history/`.

Abgrenzung:

* `state.md`: Was gilt aktuell?
* `decisions.md`: Warum wurde eine wesentliche Entscheidung getroffen, geändert oder verworfen?
* `history/`: Was wurde bei einem `project close` seit dem letzten Abschluss verändert?

Ein ADR ist erforderlich, wenn eine Entscheidung wesentliche Auswirkungen hat auf:

* Auswahl, Ausschluss oder Priorisierung von Quellen,
* Umfang oder Reihenfolge der Ingestion,
* Interpretation, Modell oder zentrale Annahmen,
* Struktur zentraler Arbeitsartefakte,
* Zielgruppe, Format oder Inhalt einer Distribution,
* Übergang eines Artefakts nach `03_dist/`,
* irreversible oder nur schwer rückgängig zu machende Schritte.

Kleine, lokale und leicht reversible Arbeitsentscheidungen benötigen keinen ADR. Sie können in der betroffenen Arbeitsdatei oder in `state.md` dokumentiert werden.

Decisions werden in einer Datei laufend fortgeschrieben.

template pro Decision:

```text
## ADR-001 Kurze bezeichnung

(DD.MM.YYYY hh:mm)
Ausführung

## ADR-002 Kurze bezeichnung

(DD.MM.YYYY hh:mm)
Ausführung
```

Die Nummer wird fortlaufend vergeben. Bestehende ADRs werden nicht gelöscht oder inhaltlich umgeschrieben. Statusänderungen, Korrekturen oder ersetzende Entscheidungen werden nachvollziehbar ergänzt oder durch einen neuen ADR dokumentiert.

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

* auf einer mit dem Benutzer abgestimmten Quellenauswahl basiert,
* relevante freigegebene Quellen im erforderlichen Umfang ingestiert wurden,
* wesentliche offene Fragen und Widersprüche geklärt oder transparent ausgewiesen sind,
* Zielgruppe, Zweck und Zielformat mit dem Benutzer abgestimmt sind,
* den aktuellen Auftrag vollständig erfüllt,
* ohne interne Arbeitsnotizen verständlich ist,
* keine ungeklärten Platzhalter enthält,
* keine als Fakten formulierten unbelegten Annahmen enthält,
* notwendige Quellenangaben enthält,
* sprachlich und strukturell geprüft wurde,
* im vorgesehenen Zielformat nutzbar ist.

Ist der Reifegrad eindeutig, schlägt der Agent zunächst konkrete Distributionsoptionen vor. Erst nach Auswahl oder Bestätigung durch den Benutzer schlägt er vor, das gewählte Ergebnis nach `03_dist/` zu kopieren.

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

`project start` ist der einfachste und empfohlene Einstiegspunkt in jede Sitzung. Bei Unklarheit, welcher Befehl zu Beginn passend ist, wird immer `project start` verwendet.

## `project start`

Beispiele:

```text
project start
start
Lass uns anfangen.
```

Ablauf:

1. Prüfe, ob `02_work/state.md` existiert.
2. **Falls `state.md` nicht existiert (Erststart):**

   a. Führe mit dem Benutzer die Klärung gemäß Abschnitt `Projektstart` oben durch (Ziel, Ergebnisse, Zielgruppe, Erfolg, Kontext und Grenzen, Ausgangslage, Startbereitschaft).
   b. Lege auf Basis der Antworten `02_work/project-brief.md` und `02_work/state.md` an.
   c. Aktualisiere anschließend `README.md` im Projektwurzelverzeichnis, sodass sie das konkrete Projekt beschreibt (Zweck, Zielgruppe, angestrebte Ergebnisse) statt der generischen Vorlagenbeschreibung. Die Abschnitte zu Projektstruktur und Befehlen bleiben inhaltlich erhalten.
   d. Prüfe, ob `.template-version` bereits existiert. Falls nicht, frage den Benutzer, ob dieses Projekt mit dem öffentlichen Projekt-Template aktuell halten will (es wird dann mit `https://github.com/ag-constructiva/agentic-project-template` verknüpft und kann aktualisiert werden. Lege nach Zustimmung `.template-version` an — Vorgehen wie in [UPDATE.md](UPDATE.md), Schritt 2b, beschrieben.
   e. Mache anschließend einen konkreten Vorschlag für den nächsten Schritt und warte auf Bestätigung, bevor Quellen ingestiert oder größere Arbeitsstrukturen angelegt werden.
3. **Falls `state.md` bereits existiert (Wiedereinstieg):**

   a. Lies `state.md`, insbesondere `Current Goal`, `Last Work`, `Open Questions` und `Next Actions`.
   b. Prüfe kurz `01_sources/` im Vergleich zum `source-index.md` auf neue oder veränderte, noch nicht inventarisierte Dateien. Dies ist eine reine Dateiprüfung, keine inhaltliche Auswertung.
   c. Falls neue oder veränderte Quellen erkannt wurden: weise den Benutzer knapp darauf hin und frage, ob der Workspace mittels `project update` aktualisiert werden soll.
   d. Falls keine neuen Quellen erkannt wurden: fasse knapp Ziel, letzten Arbeitsstand und sinnvolle nächste Schritte zusammen, ohne automatisch `project update` anzustoßen.
4. Verändere keine Dateien unter `01_sources/`, `02_work/decisions.md` oder `03_dist/` im Rahmen von `project start`, außer im Erststart gemäß Schritt 2.

---

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
Prüfe, ob es neues relevantes Wissen gibt.
```

Ablauf:

1. Lies `state.md` und `source-index.md`.
2. Prüfe vorhandene Quellen unter `01_sources/` zunächst nur auf:

   * neue Dateien,
   * veränderte Dateien,
   * bisher nicht inventarisierte Dateien,
   * aktuellen Ingestion-Status.
3. Aktualisiere das Quelleninventar in `source-index.md`, ohne neue Quellen automatisch vollständig zu ingestieren.
4. Berichte dem Benutzer, welche Quellen vorhanden sind, und schlage eine priorisierte Ingestion-Auswahl vor.
5. Werte nur Quellen aus, die bereits freigegeben sind oder deren Ingestion durch die aktuelle Benutzeranweisung eindeutig beauftragt wurde.
6. Dokumentiere für jede bearbeitete Quelle Status und ingestierten Umfang im Quellenindex.
7. Prüfe bestehende Quellenreferenzen.
8. Externe Recherche erfolgt nur nach den Regeln unter `Externe Quellen`.
9. Bereite neues oder verändertes Wissen zunächst unter `02_work/` auf.
10. Ergänze, korrigiere oder entferne dort überholte Inhalte und Verweise.
11. Dateien unter `01_sources/` werden niemals verändert oder gelöscht.
12. Vergleiche neues Wissen mit:

    * aktuellen Annahmen,
    * Entscheidungen,
    * Erkenntnissen,
    * offenen Fragen,
    * bestehenden Artefakten.
13. Markiere:

    * neue Erkenntnisse,
    * veraltete Aussagen,
    * Widersprüche,
    * mögliche Auswirkungen,
    * noch nicht ingestierte relevante Quellen.
14. Löse eindeutige offene Fragen und Widersprüche. Lege verbleibende fachliche oder geschäftliche Entscheidungen dem Benutzer mit konkretem Vorschlag vor.
15. Aktualisiere `state.md`.
16. `03_dist/` bleibt unverändert, bis Quellenauswahl, offene Punkte und Ergebnisform mit dem Benutzer abgestimmt sind.
17. Schlage erst danach geeignete Distributionsartefakte vor.
18. Berichte knapp:

    * welche Quellen inventarisiert wurden,
    * welche Quellen ingestiert oder zurückgestellt wurden,
    * was sich im Arbeitswissen geändert hat,
    * welche Widersprüche oder Fragen offen bleiben,
    * welche nächsten Ingestion- oder Distributionsentscheidungen anstehen.

---

## `project close`

Beispiele:

```text
project close
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
8. Prüfe den Quellenstand: inventarisiert, freigegeben, ingestiert, teilweise ingestiert, zurückgestellt oder offen.
9. Prüfe, ob relevante Quellen noch nicht ingestiert und wesentliche Fragen oder Widersprüche noch offen sind.
10. Prüfe erst danach, ob distributionsfähige Ergebnisse unter `02_work/` liegen.
11. Falls eine Distribution sinnvoll erscheint, schlage dem Benutzer konkrete Zielartefakte, Formate und Varianten vor.
12. Benenne erst nach dieser Abstimmung eindeutig distributionsfähige Ergebnisse und schlage vor, sie nach `03_dist/` zu kopieren.
13. Kopiere oder überschreibe keine Datei ohne ausdrückliche Zustimmung des Benutzers.
14. Verschiebe keine Arbeitsdateien automatisch.
15. Bei unklarem Reifegrad:

    * keine Distribution vorschlagen,
    * offene Qualitäts- oder Inhaltsfragen in `state.md` dokumentieren.
16. Teile dem Benutzer knapp mit:

    * was festgehalten wurde,
    * wie der Quellen- und Ingestion-Stand ist,
    * welche offenen Fragen oder Widersprüche bestehen,
    * welche Ergebnisse distributionsfähig erscheinen,
    * welche Distributionsoptionen vorgeschlagen werden,
    * für welche Distribution eine Zustimmung benötigt wird,
    * wo sinnvoll weitergearbeitet werden kann.


`project close` beendet das Thema nicht dauerhaft. Es erzeugt einen belastbaren Wiedereinstiegspunkt.

---

## `update agentic-project-template`

Beispiele:

```text
update agentic-project-template
Update project template
Gibt es ein Update für das Projekt-Template?
```

**Vor Ausführung dieses Befehls: Lies [UPDATE.md](UPDATE.md) vollständig und folge dem dortigen Ablauf Schritt für Schritt.** UPDATE.md enthält das vollständige Protokoll dieses Befehls (Prüfung auf neue Version, Abstimmung mit dem Benutzer, Übernahme je Datei, Aktualisierung von `.template-version`) und wird nur bei Ausführung dieses Befehls gelesen — nicht bei anderen Commands.
