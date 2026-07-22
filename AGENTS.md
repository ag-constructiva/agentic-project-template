# Briefing

## Sinn und Zweck

Dieses Wissensprojekt erstellt Ergebnisse aus Wissensarbeit.

---

## Projektstart

Vor Arbeitsbeginn: Projektauftrag mit Nutzer klären.

Ziel: kein vollständiges Projektkonzept, sondern klares gemeinsames Verständnis für nächsten Arbeitsschritt.

Klären:

1. **Ziel**
   Was soll das Projekt erreichen, klären, ermöglichen?

2. **Ergebnisse**
   Welche konkreten Ergebnisse könnten entstehen?

3. **Zielgruppe**
   Für wen, wie genutzt?

4. **Erfolg**
   Woran Projekterfolg erkennbar?

5. **Kontext und Grenzen**
   Rahmenbedingungen, Abhängigkeiten, bewusste Nicht-Ziele?

6. **Ausgangslage**
   Welche Quellen, Vorarbeiten, Entscheidungen, offene Fragen existieren bereits?

7. **Startbereitschaft**
   Direkt mit vorhandenen Quellen arbeiten → weitere Quellen sammeln → erst Projektauftrag schärfen?

Nur relevante Informationen für nächsten Schritt erfragen. Unnötige Vorabplanung vermeiden.

Auf Antwort-Basis: schlanke initiale Arbeitsstruktur unter `02_work/` vorschlagen — vorläufig, veränderbar mit wachsendem Verständnis.

Initialer Projektstand dokumentiert:

* was das Projekt erreichen soll,
* welche Ergebnisse aktuell angestrebt werden,
* welche Quellen verfügbar/bereits ausgewählt,
* welche Annahmen und Entscheidungen gelten,
* woran aktuell gearbeitet wird,
* welche Fragen offen sind,
* was als Nächstes sinnvoll ist.

Danach: konkreter Vorschlag für nächsten Schritt → auf Bestätigung warten → Quellen ingestieren oder größere Arbeitsstrukturen anlegen.

Startdateien (Minimum):

```text
02_work/
├── project-brief.md
├── state.md
```

Mehr zu state.md siehe unten.

---

## Arbeitsweise

Quellen, Arbeitsstände und fertige Ergebnisse strikt trennen.

Maximen:

1. **Quellen werden niemals verändert.**
2. **Quellen werden zuerst inventarisiert, erst nach Nutzer-Auswahl ingestiert.**
3. **Wissensarbeit entsteht zuerst unter `02_work/`; Distribution nach `03_dist/` erst nach gemeinsamer Klärung.**
4. **Fertige Ergebnisse sind eigenständig verständlich und nutzbar.**
5. **Belegte Aussagen, Interpretationen, Annahmen und Entscheidungen unterscheidbar dokumentieren.**
6. **Der aktuelle Arbeitsstand bleibt jederzeit wiederaufnehmbar** — Pausieren/Fortsetzen darf kein relevantes Wissen, keine Entscheidung, keine offene Frage kosten.

---

## Priorität von Anweisungen

Bei Widersprüchen:

1. Übergeordnete System-, Sicherheits- und Plattformvorgaben
2. Explizite aktuelle Benutzeranweisung
3. Unveränderlichkeit der Dateien unter `01_sources/`
4. Dieses Briefing
5. Weiterhin gültige Entscheidungen in `02_work/state.md`
6. Bestehende Inhalte unter `02_work/`
7. Selbstständige Annahmen des Agenten

Neue Benutzeranweisung darf frühere Entscheidungen ersetzen — Änderung in `state.md` unter `Decisions` dokumentieren.

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

Nur bei ausdrücklichem Nutzerwunsch oder ausdrücklicher Bereitstellung als Projektquelle: neue Dateien unter `01_sources/` ablegen.

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

Dateien in `02_work/` dürfen aktualisiert, umstrukturiert, zusammengeführt, bereinigt werden — relevante Begründungen, Gegenpositionen, Unsicherheiten, offene Fragen dabei nicht verlieren.

`02_work/` startet flach, ohne Themenordner. Entstehen zu einem Thema mehrere zusammengehörige Arbeitsdateien (z. B. Textinventar, Entwurf, offene Fragen zur selben Seite): thematischen Unterordner vorschlagen (z. B. `02_work/leistungen/`) — nicht vorab, erst wenn durch tatsächlich anfallende Dateien gerechtfertigt. Feste Unterordner (`history/`, `archive/`, `assets/`, `build/`) bleiben unberührt.

Prüfung nicht laufend bei jeder neuen Datei — spätestens bei `project update` und `project close`.

Dateien nicht automatisch löschen. Inaktive Arbeitsstände: nach `02_work/archive/` verschieben.

### `03_dist/`

Enthält distributionsfähige Ergebnisse:

* freigabefähige Dokumente,
* Präsentationen,
* Websites,
* Konzepte,
* Prompts,
* Berichte,
* andere eigenständig nutzbare Artefakte.

Ergebnis unter `03_dist/` muss ohne Zugriff auf `01_sources/` und `02_work/` verständlich und nutzbar sein.

Erforderliche Quellenangaben bleiben Bestandteil des Ergebnisses. Öffentliche, zugängliche Referenzen vor lokalen Projektpfaden.

Bearbeitbare Arbeitsdateien bleiben unter `02_work/`. Distributionsfähige Ergebnisse nach `03_dist/` **kopieren**, nicht verschieben — verhindert gebrochene Links, erhält Arbeitskontext.

Kein Ergebnis unter `03_dist/` unmittelbar nach Sichtung/Ingestion von Quellen. Vor jeder Distribution: Wissen, offene Fragen, Widersprüche, Zielgruppe, Format, Verwendungszweck mit Nutzer klären.

Auch `03_dist/` startet flach. Fallen zu einem Thema mehrere zusammengehörige distributionsfähige Artefakte an (z. B. Bericht, Präsentation, Assets zum selben Ergebnis): thematischen Unterordner vorschlagen, nicht vorab anlegen. Prüfung spätestens bei `project update` und `project close`, nicht bei jeder einzelnen Distribution.

### `.template-version`

Enthält, sofern Projekt aus dem öffentlichen Template [`agentic-project-template`](https://github.com/ag-constructiva/agentic-project-template) hervorgegangen: zuletzt synchronisierten Stand des Templates.

Format:

```text
repo: https://github.com/ag-constructiva/agentic-project-template
commit: <commit-hash>
synced: YYYY-MM-DD
```

Nur durch Befehl `update agentic-project-template` angelegt/aktualisiert. Kein Bestandteil der Wissensarbeit; nicht unter `01_sources/`, `02_work/` oder `03_dist/`.

### `UPDATE.md`

Vollständiges Ablaufprotokoll für Befehl `update agentic-project-template`, nur für den Agenten. Nur bei Ausführung dieses Befehls gelesen. Kein Bestandteil der Wissensarbeit; nicht unter `01_sources/`, `02_work/` oder `03_dist/`. Menschenlesbare Nutzungsinfos: `README.md`.

---

## Quellenklassen

### Primärquellen

Unveränderte Dateien unter:

```text
01_sources/
```

### Benutzerangaben

Informationen, die der Nutzer im Gespräch mitteilt.

Als Quelle nutzbar, müssen aber als Benutzerangabe erkennbar bleiben.

Beispiel:

```markdown
Quelle: Benutzerangabe vom 2026-07-22
```

### Externe Quellen

Öffentliche Websites, Dokumentationen, Studien oder andere recherchierte Inhalte.

Externe Recherche nur:

* auf ausdrückliche Nutzeranweisung,
* wenn für Auftrag eindeutig erforderlich,
* oder wenn übergeordnete Vorgaben aktuelle Verifikation verlangen.

Neue externe Quellen nicht automatisch unter `01_sources/` speichern.

Zunächst dokumentiert in:

```text
02_work/source-candidates.md
```

Eintrag enthält mindestens:

* Titel,
* URL,
* Herausgeber/Autor, sofern bekannt,
* Veröffentlichungsdatum, sofern bekannt,
* Abrufdatum,
* kurze Relevanzbewertung.

### Agentenableitungen

Zusammenfassungen, Interpretationen, Schlussfolgerungen des Agenten sind keine Quellen.

Müssen auf Quellen oder ausdrücklich gekennzeichneten Annahmen basieren.

### Quellenglaubwürdigkeit

Nutzer kann jeder Quelle unabhängig von ihrer Klasse eine Glaubwürdigkeitseinstufung zuweisen: `LOW`, `MEDIUM`/`MED` oder `HIGH`.

Erkennung:

1. **Dateiname**: enthält `LOW`, `MEDIUM`, `MED` oder `HIGH` vollständig großgeschrieben als eigenständigen Bestandteil (getrennt durch `-`, `_` oder Leerzeichen) → Einstufung durch Nutzer.
   Beispiel: `interview-notizen-HIGH.md`
2. **Inhaltliche Annotation**: erkennbarer Hinweis in ersten Zeilen (z. B. `Glaubwürdigkeit: MEDIUM`) → ebenfalls Einstufung durch Nutzer.

Inhaltliche Annotation hat Vorrang vor Dateiname.

Erkannte Einstufung: im Quellenindex (`02_work/source-index.md`) festhalten, bei Gewichtung von `Belegte Erkenntnisse`/`Interpretationen` berücksichtigen. Fehlt Einstufung: Quelle gilt als nicht eingestuft — nicht gleichbedeutend mit `MEDIUM`.

#### Konsequenzen der Einstufung

* **HIGH**: Aussagen gelten als belegte Grundlage. Agent baut ohne Rückfrage darauf auf.
* **MEDIUM**: Aussagen nutzbar. Agent weist darauf hin, schlägt konkret vor: weitere Quellen beisteuern oder externe Recherche zur Bestätigung (nur nach Regeln unter `Externe Quellen`, ausdrückliche Anweisung erforderlich).
* **LOW**: Jedes Arbeitsergebnis unter `02_work/`, das darauf beruht, erhält sichtbaren Warnhinweis (z. B. „> Warnhinweis: Aussage beruht auf einer Quelle mit geringer Glaubwürdigkeit"). Zusätzlich: offene Aufgabe, weitere Evidenz zu beschaffen — unter `Offene Fragen` in der Arbeitsdatei sowie unter `Open Questions`/`Next Actions` in `state.md`. Bleibt bestehen, bis Nutzer ausdrücklich anders festlegt (z. B. Quelle trotz geringer Glaubwürdigkeit als ausreichend akzeptiert).

Fehlt Einstufung: keine dieser Konsequenzen automatisch.

---

## Quellenaufnahme und Ingestion

Quellen nicht automatisch vollständig einlesen, auswerten, verdichten. Stufenweise.

### 1. Quelleninventar erstellen

Zunächst nur prüfen, welche Quellen vorhanden sind. Soweit technisch möglich erfassen:

* Dateiname oder Bezeichnung,
* Typ und Format,
* Größe, Änderungsdatum oder Hash,
* grober erkennbarer Gegenstand,
* möglicher Bezug zum aktuellen Ziel,
* aktueller Ingestion-Status.

Dient der Orientierung — noch keine vollständige inhaltliche Auswertung.

### 2. Ingestion vorschlagen und abstimmen

Auf Inventar-Basis vorschlagen:

* welche Quellen voraussichtlich relevant,
* Reihenfolge der Ingestion,
* welche Quellen zurückgestellt werden können,
* vollständige oder selektive Ingestion sinnvoll?

Vor erstmaliger Ingestion einer Quelle: Auswahl mit Nutzer abstimmen. Explizite aktuelle Benutzeranweisung kann Ingestion unmittelbar freigeben.

### 3. Ingestion nachvollziehbar durchführen

Im Quellenindex mindestens einer dieser Zustände je Quelle:

* `inventarisiert` — erkannt, noch nicht inhaltlich ausgewertet,
* `zur-ingestion-vorgeschlagen` — vom Agenten empfohlen,
* `freigegeben` — vom Nutzer ausgewählt,
* `teilweise-ingestiert` — nur relevante Teile ausgewertet,
* `vollständig-ingestiert` — im erforderlichen Umfang vollständig ausgewertet,
* `zurückgestellt` — aktuell bewusst nicht auszuwerten,
* `nicht-relevant` — für aktuelles Ziel nachweislich nicht erforderlich,
* `fehlerhaft` — Ingestion technisch/inhaltlich nicht möglich.

Bei teilweiser Ingestion: dokumentieren, welche Seiten/Abschnitte/Bereiche/Daten berücksichtigt wurden.

### 4. Wissen unter `02_work/` aufbereiten

Ingestierte Inhalte zunächst nur unter `02_work/` verarbeiten. Entstehen:

* Extraktionen und strukturierte Notizen,
* belegte Erkenntnisse,
* Interpretationen und Annahmen,
* Quellenvergleiche,
* offene Fragen,
* Widersprüche und Risiken,
* mögliche Zielbilder und Ergebnisvarianten.

Erste Verdichtung ist Arbeitsstand, kein distributionsfähiges Ergebnis.

### 5. Offene Punkte klären

Vor Distribution prüfen:

* Welche relevanten Quellen noch nicht ingestiert?
* Welche Aussagen unklar, unbelegt, widersprüchlich?
* Welche Entscheidungen benötigen fachliche/geschäftliche Bewertung?
* Welche Zielgruppe, Nutzungssituation, Ergebnisform werden benötigt?
* Welche Inhalte müssen ergänzt, verworfen, priorisiert werden?

Eindeutige Punkte selbstständig lösen. Verbleibende Entscheidungen Nutzer konkret mit Vorschlag vorlegen.

### 6. Distribution gemeinsam festlegen

Erst nach Klärung konkrete Artefakte für `03_dist/` vorschlagen, z. B.:

* Ziel und Zweck des Ergebnisses,
* Zielgruppe,
* Format,
* Umfang und Struktur,
* Varianten oder Priorisierung,
* Dateiname und Zielformat.

Für Erstellung, Kopie oder Aktualisierung unter `03_dist/`: Zustimmungspflicht aus `Artefakte und Reifegrad`.

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

Ohne präzisere Fundstelle:

```markdown
Quelle: [Dateiname](../01_sources/dateiname.ext)
```

### Webquellen

```markdown
Quelle: Titel, URL, veröffentlicht am YYYY-MM-DD, abgerufen am YYYY-MM-DD
```

Nicht vorhandene Angaben weglassen, nicht erfinden.

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

Direkte Zitate als Zitate kennzeichnen. Übersetzungen als Übersetzung kenntlich machen.

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

Bei umfangreichen Arbeitsdateien:

```markdown
## Belegte Erkenntnisse

## Interpretationen

## Annahmen

## Entscheidungen

## Offene Fragen

## Widersprüche und Risiken
```

Nicht jede Datei muss alle Abschnitte enthalten. Nicht belegte Aussagen nicht als gesicherte Fakten formulieren.

---

## Verlinkung von Arbeitsdateien

Verknüpfungen über relative Markdown-Links.

Jede Arbeitsdatei verlinkt, soweit relevant:

* ihre Primärquellen,
* verwendete externe Quellen,
* verwandte Arbeitsdateien,
* daraus entstandene Ergebnisse unter `03_dist/`.

Inhalte nicht unnötig duplizieren — kanonische Inhalte an einer Stelle pflegen, von anderen Dateien aus verlinken.

Wiki-spezifische Syntax oder proprietäre Linkformate nicht vorausgesetzt.

---

## Dateinamenskonventionen

Dateinamen:

* kleingeschrieben,
* aussagekräftig,
* mit Bindestrichen getrennt,
* ohne Begriffe wie `final`, `neu`, `wirklich-final` oder fortlaufende Versionszusätze.

Beispiele:

```text
02_work/zielgruppenanalyse.md
02_work/zielgruppenanalyse-alternativen.md
02_work/quellenbewertung-ki-brownfield.md
03_dist/positionierungskonzept-2026-07-22.md
```

Aktueller Stand einer Arbeitsdatei: grundsätzlich in derselben Datei pflegen.

Varianten nur trennen, wenn bewusst parallel bestehend.

---

## Quellenindex

Quellenstand gepflegt in:

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

Für lokale Quellen soweit möglich Hash verwenden. Andernfalls Dateigröße und Änderungsdatum.

Index dient dazu:

* neue Quellen zu erkennen,
* veränderte Quellen zu erkennen,
* Ingestion-Status jeder Quelle nachzuvollziehen,
* ausgewerteten Umfang sichtbar zu machen,
* Verwendungen nachzuvollziehen,
* nicht ausgewertete oder zurückgestellte Quellen sichtbar zu machen.

Quelle gilt nicht allein deshalb als ingestiert, weil technisch geöffnet, aufgelistet oder oberflächlich geprüft.

Quellenindex ersetzt keine präzisen Referenzen in Arbeitsdateien.

---

## Sprache

Outputs auf Deutsch, sofern nicht anders verlangt.

Englischsprachige Fachbegriffe, Eigennamen, Zitate im Original übernehmen, wenn präziser oder im Fachkontext üblich.

Übersetzte Zitate als Übersetzung kennzeichnen.

---

## Arbeitszustand

Aktueller Zustand gepflegt in:

```text
02_work/state.md
```

`state.md` ist kein chronologisches Protokoll — nur aktuell relevanter Stand.

Bei jeder Aktualisierung vollständig überschreiben, nicht ergänzen/anhängen. Überholte/erledigte Inhalte entfernen statt kumulativ stehen lassen; Historie und ADRs gehören nach `02_work/history/` bzw. `02_work/decisions.md`, nicht in `state.md`.

`state.md` nicht nach jeder einzelnen wesentlichen Änderung sofort schreiben. Agent merkt sich wesentliche Änderungen zunächst nur im Gespräch (Kontext), schreibt gesammelt:

* bei `project start` (Wiedereinstieg, vor neuer Arbeit),
* bei `project update`,
* bei `project close`,
* bei `state save` (siehe `User Commands`),
* wenn Nutzer dies verlangt,
* sowie sofort bei neuem Widerspruch/Risiko, das sonst bei abruptem Sitzungsende verloren ginge.

Änderung ist wesentlich (spätestens gesammelt übernehmen), wenn sie Ziel, Wissensstand, eine Entscheidung, einen offenen Punkt, ein Risiko, eine nächste Aktion oder eine aktive Datei verändert.

Keine Aktualisierung nötig bei:

* rein lesenden Tätigkeiten,
* kleinen Formulierungsänderungen,
* folgenlosen Formatkorrekturen,
* unveränderten Rechercheergebnissen.

Zwischen Schreibpunkten bleibt `state.md` auf Stand des letzten Schreibvorgangs; Agent hält aktuelleren Zwischenstand im Gespräch nach, gleicht spätestens beim nächsten Schreibpunkt ab. Bricht Sitzung unerwartet ab: ungeschriebener Zwischenstand kann verloren gehen — bewusst in Kauf genommener Tradeoff für geringeren Tokenverbrauch.

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

Überholte Entscheidungen nicht kommentarlos entfernen — durch aktuell gültige ersetzen, zum zugehörigen ADR referenzieren. `state.md` enthält nur gegenwärtig gültige Entscheidung; dauerhafte Entscheidungshistorie liegt in `02_work/decisions.md`.

---

## Architecture Decision Records (ADR)

Dauerhafte Entscheidungen als append-only ADRs dokumentiert unter:

```text
02_work/decisions.md
```

ADRs halten fest, warum eine Entscheidung getroffen wurde. Ersetzen weder `state.md` noch `02_work/history/`.

Abgrenzung:

* `state.md`: Was gilt aktuell?
* `decisions.md`: Warum wurde eine wesentliche Entscheidung getroffen, geändert, verworfen?
* `history/`: Was wurde bei `project close` seit dem letzten Abschluss verändert?

ADR erforderlich, wenn Entscheidung wesentliche Auswirkungen hat auf:

* Auswahl, Ausschluss oder Priorisierung von Quellen,
* Umfang oder Reihenfolge der Ingestion,
* Interpretation, Modell oder zentrale Annahmen,
* Struktur zentraler Arbeitsartefakte,
* Zielgruppe, Format oder Inhalt einer Distribution,
* Übergang eines Artefakts nach `03_dist/`,
* irreversible oder schwer rückgängig zu machende Schritte.

Kleine, lokale, leicht reversible Arbeitsentscheidungen: kein ADR nötig — dokumentierbar in Arbeitsdatei oder `state.md`.

Decisions laufend in einer Datei fortschreiben.

Template pro Decision:

```text
## ADR-001 Kurze bezeichnung

(DD.MM.YYYY hh:mm)
Ausführung

## ADR-002 Kurze bezeichnung

(DD.MM.YYYY hh:mm)
Ausführung
```

Nummer fortlaufend. Bestehende ADRs nicht löschen oder umschreiben. Statusänderungen, Korrekturen, ersetzende Entscheidungen: ergänzen oder neuen ADR anlegen.

---

## Historie

Keine Sitzungsprotokolle je Interaktion.

Bei `project close` nur History-Eintrag, wenn seit letztem Eintrag substanzieller Fortschritt: Ziel verändert, nennenswerte Arbeit/Wissen entstanden, oder Widerspruch/Risiko aufgelöst.

Reine Änderungen an `Active Files`/`Open Questions` lösen für sich keinen Eintrag aus — entstehen laufend, bereits in `state.md` aktuell. Entscheidungen allein auch nicht — dauerhaft in `decisions.md`. Reine Template-/Infrastruktur-Updates (z. B. `update agentic-project-template`) auch nicht — keine Wissensarbeit. Kein substanzieller Fortschritt (reine Statusabfragen, reine Umpriorisierung offener Punkte, reine Template-Syncs, unveränderte Zwischenstände) → kein Eintrag; `state.md` trotzdem aktualisieren.

Eintrag wiederholt unveränderte Abschnitte nicht vollständig. Unverändert seit letztem Eintrag (`Goal`, `Open Questions` o. ä.) → darauf verweisen (z. B. „Unverändert gegenüber [vorheriger Eintrag](2026-07-22-1620.md)"), nicht erneut ausschreiben.

```text
02_work/history/YYYY-MM-DD-HHMM.md
```

Append-only:

* bestehende History-Dateien nicht verändern,
* frühere Einträge nicht löschen,
* Korrekturen durch neuen Eintrag.

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

Historie hält nur wesentliche Änderungen fest — kein vollständiges Gesprächsprotokoll.

---

## Assets und Binärformate

Verwende:

```text
02_work/assets/
```

für bearbeitete Bilder, Diagramme, andere interne Medien.

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

für Medien als Bestandteil eines distributionsfähigen Ergebnisses.

Bearbeitbare Quelldateien bleiben unter `02_work/`. Exportierte Endformate nach `03_dist/` kopiert.

Temporäre Build-Dateien: bereinigen, wenn reproduzierbar und nicht mehr erforderlich. Primärquellen und relevante Arbeitsstände nicht löschen.

---

## Widersprüche

Bei einem Widerspruch:

1. Keine Aussage stillschweigend verändern.
2. Beide Positionen dokumentieren.
3. Herkunft, Kontext, Evidenz ermitteln.
4. Prüfen, ob Aussage:

   * veraltet,
   * kontextabhängig,
   * unvollständig,
   * schwächer belegt
     ist.
5. Widerspruch selbstständig lösen, wenn Evidenz und Prioritätsregeln eindeutig.
6. Lösung und Begründung dokumentieren.
7. Nutzer konkrete Entscheidung vorlegen, wenn fachliche/geschäftliche Bewertung nötig bleibt.

Ungelöster Widerspruch festgehalten:

* in betroffener Arbeitsdatei,
* in `02_work/state.md` unter `Risks and Conflicts`,
* ggf. unter `Open Questions`.

---

## Umgang mit Unsicherheit

Fehlende Informationen nicht erfinden.

Aufgabe trotz Unsicherheit sinnvoll fortführbar: ausdrücklich gekennzeichnete Arbeitsannahme verwenden.

Beispiel:

```markdown
Annahme: Für die weitere Analyse wird zunächst davon ausgegangen, dass …
```

Nutzerentscheidung nur erforderlich, wenn:

* mehrere plausible Optionen zu wesentlich verschiedenen Ergebnissen führen,
* geschäftliche, fachliche oder normative Bewertung notwendig,
* eine irreversible Aktion betroffen,
* ein distributionsfähiges Ergebnis sonst irreführend wäre.

Kleine oder leicht reversible Entscheidungen: Agent trifft selbstständig, dokumentiert.

---

## Artefakte und Reifegrad

Ergebnis distributionsreif, wenn:

* auf mit Nutzer abgestimmter Quellenauswahl basiert,
* relevante freigegebene Quellen im erforderlichen Umfang ingestiert,
* wesentliche offene Fragen/Widersprüche geklärt oder transparent ausgewiesen,
* Zielgruppe, Zweck, Zielformat mit Nutzer abgestimmt,
* aktuellen Auftrag vollständig erfüllt,
* ohne interne Arbeitsnotizen verständlich,
* keine ungeklärten Platzhalter enthält,
* keine als Fakten formulierten unbelegten Annahmen enthält,
* notwendige Quellenangaben enthält,
* sprachlich und strukturell geprüft,
* im vorgesehenen Zielformat nutzbar.

Bei eindeutigem Reifegrad: zunächst konkrete Distributionsoptionen vorschlagen. Erst nach Auswahl/Bestätigung durch Nutzer: Kopie nach `03_dist/` vorschlagen.

Vor dem Kopieren: ausdrückliche Nutzer-Zustimmung erforderlich.

Ohne Zustimmung:

* Ergebnis bleibt unter `02_work/`,
* keine Datei unter `03_dist/` erstellt oder überschrieben,
* mögliche Distribution unter `Next Actions` in `state.md` festgehalten.

Bei unklarem Reifegrad: Ergebnis bleibt unter `02_work/`, als offener Punkt dokumentiert.

Bearbeitbare Arbeitsdateien nie automatisch nach `03_dist/` verschoben.

Bestehende Dateien unter `03_dist/` nicht ohne ausdrückliche Zustimmung überschreiben. Bei Aktualisierung eine Variante vorschlagen:

* bestehende Datei ersetzen,
* datierte neue Version erzeugen.

Gewählte Variante dokumentieren.

---

# User Commands

Semantische Befehle — Nutzer muss sie nicht exakt schreiben, gleichbedeutende natürliche Formulierungen gültig.

`project start` ist einfachster, empfohlener Einstiegspunkt in jede Sitzung. Bei Unklarheit, welcher Befehl passt: immer `project start`.

## `project start`

Beispiele:

```text
project start
start
Lass uns anfangen.
```

Ablauf:

1. Prüfen, ob `02_work/state.md` existiert.
2. **Falls nicht (Erststart):**

   a. Klärung mit Nutzer gemäß Abschnitt `Projektstart` oben (Ziel, Ergebnisse, Zielgruppe, Erfolg, Kontext und Grenzen, Ausgangslage, Startbereitschaft).
   b. Auf Antwort-Basis `02_work/project-brief.md` und `02_work/state.md` anlegen.
   c. `README.md` im Projektwurzelverzeichnis aktualisieren: konkretes Projekt beschreiben (Zweck, Zielgruppe, angestrebte Ergebnisse) statt generischer Vorlagenbeschreibung. Abschnitte zu Projektstruktur/Befehlen inhaltlich erhalten.
   d. Prüfen, ob `.template-version` existiert. Falls nicht: fragen, ob Projekt mit öffentlichem Template aktuell gehalten werden soll (Verknüpfung mit `https://github.com/ag-constructiva/agentic-project-template`). Nach Zustimmung `.template-version` anlegen — Vorgehen wie [UPDATE.md](UPDATE.md), Schritt 2b.
   e. Konkreter Vorschlag für nächsten Schritt → auf Bestätigung warten → erst danach Quellen ingestieren oder größere Arbeitsstrukturen anlegen.
3. **Falls `state.md` existiert (Wiedereinstieg):**

   a. `state.md` lesen, insbesondere `Current Goal`, `Last Work`, `Open Questions`, `Next Actions`.
   b. `01_sources/` kurz gegen `source-index.md` auf neue/veränderte, nicht inventarisierte Dateien prüfen — reine Dateiprüfung, keine inhaltliche Auswertung.
   c. Neue/veränderte Quellen erkannt: Nutzer knapp hinweisen, fragen ob `project update` sinnvoll.
   d. Keine neuen Quellen: Ziel, letzten Arbeitsstand, sinnvolle nächste Schritte knapp zusammenfassen, ohne automatisch `project update` anzustoßen.
4. Keine Dateien unter `01_sources/`, `02_work/decisions.md` oder `03_dist/` verändern, außer im Erststart gemäß Schritt 2.

---

## `project status`

Beispiele:

```text
project status
Wo stehen wir?
Was ist hier der aktuelle Stand?
```

Ablauf:

1. `02_work/state.md` lesen.
2. Unter `Active Files` genannte Dateien prüfen.
3. Relevante Einträge im Quellenindex prüfen.
4. Weitere Dateien nur lesen:

   * `state.md` fehlt,
   * Zustand wirkt widersprüchlich,
   * aktive Dateien fehlen,
   * oder Benutzerfrage erfordert mehr Details.
5. Zusammenfassen:

   * Ziel,
   * aktuellen Stand,
   * letzte Ergebnisse,
   * offene Fragen,
   * nächste Aktionen,
   * relevante Risiken.
6. Keine Dateien verändern, außer Nutzer bittet ausdrücklich um Aktualisierung.

`state.md` offensichtlich veraltet: darauf hinweisen, nicht automatisch verändern.

---

## `state save`

Beispiele:

```text
state save
save
Halte den Zwischenstand fest.
Schreib den State jetzt.
```

Schreibt im Gespräch gehaltenen Zwischenstand sofort nach `02_work/state.md`, ohne übrige Schritte von `project close` — kein History-Eintrag, keine erneute Quellenprüfung, keine Distributionsprüfung.

Ablauf:

1. `state.md` vollständig gemäß Struktur unter `Arbeitszustand` aktualisieren, basierend auf aktuellem Gesprächsstand.
2. Keine anderen Dateien verändern.
3. Knapp bestätigen, dass Zwischenstand geschrieben wurde.

Sinnvoll als Absicherung während längerer Sitzung, wenn noch kein `project close` ansteht, ein abrupter Abbruch aber Zwischenstand kosten würde.

---

## `project update`

Beispiele:

```text
project update
Aktualisiere den Workspace.
Prüfe, ob es neues relevantes Wissen gibt.
```

Ablauf:

1. `state.md` und `source-index.md` lesen.
2. Quellen unter `01_sources/` zunächst nur prüfen auf:

   * neue Dateien,
   * veränderte Dateien,
   * bisher nicht inventarisierte Dateien,
   * aktuellen Ingestion-Status.
3. Quelleninventar in `source-index.md` aktualisieren, ohne neue Quellen automatisch vollständig zu ingestieren.
4. Nutzer berichten, welche Quellen vorhanden sind, priorisierte Ingestion-Auswahl vorschlagen.
5. Nur freigegebene oder durch aktuelle Benutzeranweisung eindeutig beauftragte Quellen auswerten.
6. Für jede bearbeitete Quelle Status/ingestierten Umfang im Quellenindex dokumentieren.
7. Bestehende Quellenreferenzen prüfen.
8. Externe Recherche nur nach Regeln unter `Externe Quellen`.
9. Neues/verändertes Wissen zunächst unter `02_work/` aufbereiten.
10. Überholte Inhalte und Verweise ergänzen, korrigieren, entfernen.
11. Dateien unter `01_sources/` niemals verändern oder löschen.
12. Neues Wissen vergleichen mit:

    * aktuellen Annahmen,
    * Entscheidungen,
    * Erkenntnissen,
    * offenen Fragen,
    * bestehenden Artefakten.
13. Markieren:

    * neue Erkenntnisse,
    * veraltete Aussagen,
    * Widersprüche,
    * mögliche Auswirkungen,
    * noch nicht ingestierte relevante Quellen.
14. Eindeutige offene Fragen/Widersprüche lösen. Verbleibende fachliche/geschäftliche Entscheidungen Nutzer mit konkretem Vorschlag vorlegen.
15. `state.md` aktualisieren.
16. `03_dist/` bleibt unverändert, bis Quellenauswahl, offene Punkte, Ergebnisform mit Nutzer abgestimmt.
17. Erst danach geeignete Distributionsartefakte vorschlagen.
18. Knapp berichten:

    * welche Quellen inventarisiert wurden,
    * welche Quellen ingestiert oder zurückgestellt wurden,
    * was sich im Arbeitswissen geändert hat,
    * welche Widersprüche/Fragen offen bleiben,
    * welche nächsten Ingestion-/Distributionsentscheidungen anstehen.

---

## `project close`

Beispiele:

```text
project close
Für heute reicht es.
Halte den Stand fest.
```

Ablauf:

1. `state.md`, aktive Dateien, relevante Quellenreferenzen lesen.
2. Alle seit letztem History-Eintrag relevanten Änderungen ermitteln.
3. Prüfen, ob unfertige Arbeitsstände existieren.
4. Prüfen, ob Entscheidungen, Annahmen, offene Fragen, Risiken korrekt dokumentiert sind.
5. `state.md` vollständig aktualisieren — alle Felder gemäß Struktur unter `Arbeitszustand`.
6. Neuer History-Eintrag unter `02_work/history/YYYY-MM-DD-HHMM.md` nur bei substanziellem Fortschritt seit letztem Eintrag (siehe `Historie`). Sonst kein Eintrag; Nutzer knapp informieren.
7. Quellenstand prüfen: inventarisiert, freigegeben, ingestiert, teilweise ingestiert, zurückgestellt oder offen.
8. Prüfen: relevante Quellen nicht ingestiert oder wesentliche Fragen/Widersprüche offen?
9. Erst danach prüfen, ob distributionsfähige Ergebnisse unter `02_work/` liegen.
10. Distribution sinnvoll: Nutzer konkrete Zielartefakte, Formate, Varianten vorschlagen.
11. Erst nach dieser Abstimmung eindeutig distributionsfähige Ergebnisse benennen, Kopie nach `03_dist/` vorschlagen.
12. Keine Datei ohne ausdrückliche Nutzer-Zustimmung kopieren oder überschreiben.
13. Keine Arbeitsdateien automatisch verschieben.
14. Bei unklarem Reifegrad:

    * keine Distribution vorschlagen,
    * offene Qualitäts-/Inhaltsfragen in `state.md` dokumentieren.
15. Nutzer knapp mitteilen:

    * was festgehalten wurde,
    * wie Quellen- und Ingestion-Stand ist,
    * welche offenen Fragen/Widersprüche bestehen,
    * welche Ergebnisse distributionsfähig erscheinen, welche Distributionsoptionen vorgeschlagen werden, wofür Zustimmung nötig ist,
    * wo sinnvoll weitergearbeitet werden kann.
16. Liegt ein History-Eintrag vor (siehe Schritt 6) und ist das Projektverzeichnis ein Git-Repo: zusätzlich eine copy-paste-fertige Ein-Zeilen-Headline aus `Completed` ableiten (z. B. „Update Zielgruppenanalyse um Marktabgleich"), nicht als „Commit-Message" bezeichnen. Kein Git-Repo oder kein History-Eintrag: entfällt.

`project close` beendet das Thema nicht dauerhaft — erzeugt belastbaren Wiedereinstiegspunkt.

---

## `update agentic-project-template`

Beispiele:

```text
update agentic-project-template
Update project template
Gibt es ein Update für das Projekt-Template?
```

**Vor Ausführung: [UPDATE.md](UPDATE.md) vollständig lesen, Ablauf dort Schritt für Schritt folgen.** UPDATE.md enthält vollständiges Protokoll (Prüfung auf neue Version, Abstimmung mit Nutzer, Übernahme je Datei, Aktualisierung von `.template-version`) — nur bei Ausführung dieses Befehls gelesen, nicht bei anderen Commands.
