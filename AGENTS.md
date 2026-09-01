# Agentenregeln

Dieses Projekt ist eine dateibasierte Workbench für Wissensarbeit. Quellen,
verdichtetes Wissen, laufende Arbeit und freigegebene Ergebnisse bleiben
getrennt und nachvollziehbar.

## Verbindliche Grundregeln

1. Dateien unter `01_sources/` niemals bearbeiten, überschreiben, umbenennen,
   verschieben oder löschen.
2. Neue oder veränderte Quellen zuerst inventarisieren; erst nach Auswahl durch
   den Nutzer oder eindeutiger aktueller Freigabe inhaltlich ingestieren.
3. Verdichtetes und wiederverwendbares Wissen unter `02_context/` pflegen.
4. Laufende Fragen, Analysen, Entwürfe und Arbeitsstände unter `03_work/`
   pflegen.
5. Ergebnisse zunächst unter `03_work/` erstellen.
6. Nach `04_dist/` nur nach ausdrücklicher Zustimmung kopieren oder dort
   bestehende Dateien ersetzen.
7. Distributionsfähige Ergebnisse müssen ohne interne Arbeitsdateien
   verständlich und nutzbar sein.
8. Belegte Aussagen, Interpretationen, Annahmen, Entscheidungen, offene Fragen
   und Widersprüche sichtbar unterscheiden.
9. Fehlende Informationen nicht erfinden. Unsicherheit als solche benennen.
10. Relevante Quellen und Arbeitsdateien nachvollziehbar referenzieren.
11. Aktuelles Ziel, Entscheidungen, offene Punkte, Risiken und nächste Schritte
    so dokumentieren, dass eine spätere Sitzung fortsetzen kann.
12. Aktuelle ausdrückliche Nutzeranweisungen können frühere Entscheidungen
    ersetzen; die Änderung in `state.md` und bei wesentlichen Entscheidungen in
    `decisions.md` festhalten.
13. Vor jeder neuen inhaltlichen Arbeit den aktuellen Projektkontext
    wiederherstellen und dem Nutzer kurz sichtbar zusammenfassen.

Bei Konflikten gilt diese Reihenfolge:

1. System-, Sicherheits- und Plattformregeln
2. aktuelle ausdrückliche Nutzeranweisung
3. Unveränderlichkeit von `01_sources/`
4. diese Datei
5. aktueller Stand und Entscheidungen unter `03_work/`
6. übriger Projektinhalt
7. eigene Annahmen

## Ordner und zentrale Dateien

```text
01_sources/   unveränderte Primärquellen
02_context/   verdichteter, wiederverwendbarer Wissenskontext
03_work/      laufende Arbeit und Arbeitszustand
04_dist/      freigegebene, eigenständig nutzbare Ergebnisse
```

Zentrale Dateien:

```text
02_context/source-index.md   Quelleninventar und Ingestion-Status
03_work/project-brief.md    Projektauftrag
03_work/state.md             aktueller Zustand
03_work/decisions.md         dauerhafte Entscheidungsbegründungen
03_work/history/             substanzielle Abschlussstände
```

`02_context/` und `03_work/` dürfen passend zum Projekt aktualisiert und
strukturiert werden. Für `03_work/` gibt es keine globale Pflichtstruktur:
Ad-hoc-Unterordner wie `analysen/`, `entwuerfe/`, `assets/`, `build/` oder
`archiv/` sind erlaubt, wenn sie einen klaren Zweck haben. Arbeitsdateien,
Quellen, Entwürfe, Medien und generierte Zwischenstände nicht ungeordnet
vermischen. Die gewählte Struktur oder besondere Ablageentscheidungen kurz in
`state.md`, einer Arbeitsdatei oder einer lokalen README dokumentieren.

Relevantes Wissen, Begründungen, Gegenpositionen und Unsicherheiten dürfen bei
der Umstrukturierung nicht verloren gehen. Inaktive Arbeit nicht automatisch
löschen, sondern nachvollziehbar archivieren.

## Quellen und Ingestion

### Quellenarten

- Primärquellen liegen unverändert unter `01_sources/`.
- Benutzerangaben dürfen als Quellen verwendet werden, müssen aber als solche
  gekennzeichnet sein.
- Externe Recherche nur auf ausdrückliche Nutzeranweisung, wenn der Auftrag sie
  eindeutig erfordert oder eine übergeordnete Regel aktuelle Verifikation
  verlangt. Neue externe Quellen zunächst in
  `02_context/source-candidates.md` dokumentieren.
- Zusammenfassungen, Interpretationen und Schlussfolgerungen des Agents sind
  keine Quellen; sie müssen auf Quellen oder gekennzeichneten Annahmen beruhen.

### Ablauf

1. Vor der Auswertung Inventar erstellen: Datei, Typ, Größe oder Hash,
   Änderungsdatum, grober Gegenstand, Bezug zum Ziel und Status.
2. Relevante Quellen und Ingestion-Reihenfolge vorschlagen.
3. Auswahl mit dem Nutzer abstimmen, sofern keine eindeutige aktuelle Freigabe
   vorliegt.
4. Nur freigegebene Quellen im erforderlichen Umfang auswerten.
5. Status und ingestierten Umfang im Quellenindex dokumentieren.
6. Erkenntnisse zuerst unter `02_context/` aufbereiten, danach in laufender
   Arbeit unter `03_work/` verwenden.
7. Neue Erkenntnisse gegen Annahmen, Entscheidungen, offene Fragen,
   Widersprüche und bestehende Ergebnisse prüfen.

Der Quellenindex erfasst mindestens Pfad, Typ, Größe oder Hash, Änderungsdatum,
Glaubwürdigkeit, Ingestion-Status, ingestierten Umfang, letzte Prüfung,
Verwendung und Hinweise. Bei `teilweise-ingestiert` immer die ausgewerteten
Seiten, Abschnitte, Tabellen oder sonstigen Grenzen nennen.

Zulässige Ingestion-Statuswerte sind:

```text
inventarisiert
zur-ingestion-vorgeschlagen
freigegeben
teilweise-ingestiert
vollständig-ingestiert
zurückgestellt
nicht-relevant
fehlerhaft
```

`teilweise-ingestiert` muss den ausgewerteten Umfang nennen. Eine Datei gilt
nicht allein durch Öffnen, Auflisten oder oberflächliche Sichtung als ingestiert.

### Glaubwürdigkeit

Eine vom Nutzer vergebene Einstufung `HIGH`, `MEDIUM`/`MED` oder `LOW` im
Dateinamen oder in den ersten Zeilen der Quelle im Quellenindex festhalten.
Eine inhaltliche Annotation hat Vorrang vor dem Dateinamen. Ohne Einstufung
keine automatische Einstufung annehmen.

- `HIGH`: als belegte Grundlage verwendbar.
- `MEDIUM`: verwendbar, Unsicherheit kenntlich machen und weitere Bestätigung
  als Option nennen.
- `LOW`: sichtbaren Warnhinweis im darauf beruhenden Ergebnis und weitere
  Evidenz als offene Aufgabe festhalten.

## Aussagearten

Arbeitsdateien müssen Aussagen nicht künstlich in getrennte Dateien verteilen,
aber die Art der Aussage sichtbar machen:

- **Belegt:** direkt aus einer Quelle ableitbar oder mehrfach gestützt.
- **Interpretation:** plausible Deutung belegter Informationen.
- **Annahme:** noch nicht belegte Arbeitshypothese.
- **Entscheidung:** bewusst festgelegte Grundlage für das weitere Vorgehen.
- **Offene Frage:** noch nicht ausreichend beantwortet.
- **Widerspruch:** nicht gleichzeitig vereinbare Aussagen oder Anforderungen.

Bei umfangreichen Dateien sind passende Abschnitte wie diese zulässig:

```markdown
## Belegte Erkenntnisse
## Interpretationen
## Annahmen
## Entscheidungen
## Offene Fragen
## Widersprüche und Risiken
```

Widersprüche nicht stillschweigend auflösen. Herkunft, Kontext und Evidenz
prüfen; bei eindeutiger Evidenz begründet lösen, sonst beide Positionen und die
notwendige Nutzerentscheidung dokumentieren.

## Referenzen und Verlinkung

Arbeitsdateien verlinken relevante Primärquellen, externe Quellen, verwandte
Arbeitsdateien und daraus entstandene Distributionen.

Im Modus `plain` relative Markdown-Links verwenden. Bei `.vault-mode` mit Wert
`obsidian` interne Links als Wikilinks schreiben. Bestehende Inhalte nicht nur
wegen eines Moduswechsels rückwirkend konvertieren.

Beispiele:

```markdown
Quelle: [quelle.pdf](../01_sources/quelle.pdf), S. 12–14
Quelle: [notiz.md](../01_sources/notiz.md), Abschnitt „Bezeichnung“
Quelle: Benutzerangabe vom 2026-09-01
Quelle: Titel, https://example.org, abgerufen am 2026-09-01
Ableitung aus:
- Quelle A, S. 4
- Quelle B, Abschnitt „Bezeichnung“
```

Nicht vorhandene Seiten, Daten oder bibliografische Angaben nicht erfinden.

## Arbeitszustand

`03_work/state.md` enthält nur den aktuell gültigen Stand, kein vollständiges
Sitzungsprotokoll. Veraltete Inhalte entfernen oder durch den aktuellen Stand
ersetzen; Historie gehört nach `history/`, Entscheidungsbegründungen nach
`decisions.md`.

Bei einer Änderung an Ziel, Wissensstand, Entscheidung, offenem Punkt, Risiko,
nächster Aktion oder aktiver Datei den Stand spätestens bei `update`, `close`,
`state save` oder Nutzeraufforderung aktualisieren. Reine Lesevorgänge und
folgenlose Formatkorrekturen erfordern keine State-Aktualisierung.

Bei drohendem Sitzungsabbruch wesentliche Änderungen sofort sichern.

Mindeststruktur:

```markdown
# State

Updated: YYYY-MM-DD HH:MM

## Current Goal
## Current State
## Last Work
## Decisions
## Open Questions
## Next Actions
## Risks and Conflicts
```

Unter `Decisions` nur aktuell gültige Entscheidungen mit Verweis auf
`03_work/decisions.md` führen.

## Context-Restore-Gate

Bei `start`, `update` und beim Beginn eines neuen Chats zu diesem Projekt gilt
vor jeder Analyse, Änderung oder Ingestion:

1. `03_work/state.md` lesen.
2. `02_context/source-index.md` auf Quellenstand, offene Ingestion und neue oder
   veränderte Quellen prüfen.
3. Die von `state.md` referenzierten aktuellen Arbeitsdateien prüfen.
4. Struktur von `03_work/` prüfen: Dateien sollen auffindbar, sinnvoll gruppiert
   und von temporären oder archivierten Inhalten getrennt sein. Bei Bedarf
   konkreten Vorschlag machen, aber nicht ohne Zustimmung umfangreich
   umorganisieren.
5. `03_work/decisions.md` für die unter `state.md` genannten oder zuletzt
   relevanten Entscheidungen lesen.
6. Einen kurzen Wiederaufnahme-Block ausgeben mit:
   - aktuellem Ziel und Projektstand,
   - letzter Arbeit,
   - aktuell gültigen Entscheidungen,
   - offenen Fragen und Risiken,
   - nicht ingestierten oder veränderten relevanten Quellen,
   - nächsten sinnvollen Schritten.
7. Erst danach mit der eigentlichen Nutzeraufgabe fortfahren.

Offene Fragen und Risiken wiederholen, auch wenn sie für die aktuelle Aufgabe
zunächst nicht blockieren. Als „bereits dokumentiert“ erkannte Punkte nicht
erneut ungeprüft entscheiden. Wenn `state.md` fehlt, zuerst `INIT.md` lesen.
Wenn State und Arbeitsdateien widersprüchlich wirken, den Widerspruch nennen
und vor einer richtungsändernden Entscheidung klären.

### Decision Records

Wesentliche Entscheidungen als append-only Einträge in
`03_work/decisions.md` dokumentieren. Das gilt insbesondere für Quellenwahl,
Ingestion-Umfang oder -Reihenfolge, zentrale Annahmen oder Modelle,
Arbeitsstruktur, Distribution, sowie irreversible oder schwer rückgängig zu
machende Schritte.

Kleine, reversible Arbeitsentscheidungen brauchen keinen eigenen Record.
Bestehende Records nicht umschreiben; Änderungen als neuen Eintrag ergänzen.

```markdown
## DR-001 Kurzbezeichnung

(DD.MM.YYYY hh:mm)
Entscheidung und Begründung
```

### History

Bei `close` nur bei substanziellem Fortschritt seit dem letzten Eintrag eine
Datei `03_work/history/YYYY-MM-DD-HHMM.md` anlegen. Kein Sitzungsprotokoll und
keine Wiederholung unveränderter Abschnitte.

```markdown
# YYYY-MM-DD HH:MM
## Goal
## Completed
## Decisions
## Open Questions
## Next Actions
## Changed Files
## Risks and Conflicts
```

## Distribution

Vor Distribution prüfen:

- vereinbarte Quellenauswahl und erforderliche Ingestion abgeschlossen,
- wesentliche offene Fragen und Widersprüche geklärt oder sichtbar ausgewiesen,
- Zielgruppe, Zweck und Format klar,
- Ergebnis eigenständig verständlich,
- keine ungeklärten Platzhalter oder unbelegten Fakten,
- Quellenangaben und sprachliche/formale Prüfung vorhanden.

Wenn diese Prüfung nicht eindeutig erfüllt ist, bleibt das Ergebnis unter
`03_work/` und wird nicht als distributionsreif bezeichnet.

Bei unklarem Reifegrad bleibt das Ergebnis unter `03_work/`. Vor dem Kopieren
nach `04_dist/` Zielartefakt, Format und Variante mit dem Nutzer abstimmen.
Bestehende Dateien in `04_dist/` nicht ohne ausdrückliche Zustimmung
überschreiben. Arbeitsdateien nicht verschieben, sondern kopieren.

## Dateinamen und Sprache

Dateinamen kleingeschrieben, aussagekräftig und mit Bindestrichen schreiben.
Keine Zusätze wie `final`, `neu` oder fortlaufende Versionsnummern für den
aktuellen Stand. Varianten nur bei bewusst parallel gepflegten Fassungen.

Deutsch verwenden, sofern der Nutzer nichts anderes verlangt. Fachbegriffe,
Eigennamen und präzise Originalzitate im Original belassen; Übersetzungen als
solche kennzeichnen.

## Projektbefehle

Normale Sprache genügt; die folgenden semantischen Befehle sind Richtwerte.

### `start` / `session start`

1. Prüfen, ob `03_work/state.md` existiert.
2. Wenn nicht: `INIT.md` vollständig lesen und dessen Ablauf befolgen.
3. Wenn vorhanden: `state.md` lesen.
4. `01_sources/` nur auf neue oder veränderte Dateien gegenüber dem
   Quellenindex prüfen; keine automatische Inhaltsauswertung.
5. Neue oder veränderte Quellen knapp melden und `update` vorschlagen.
6. Das Context-Restore-Gate vollständig ausführen.
7. Ohne neue Quellen Ziel, letzten Stand und sinnvolle nächste Schritte knapp
   zusammenfassen.
8. Beim normalen `start` keine Dateien verändern.

### `status`

1. `03_work/state.md` lesen.
2. Genannte aktive Dateien und relevante Quellenindex-Einträge prüfen.
3. Ziel, Stand, letzte Ergebnisse, offene Fragen, nächste Schritte und Risiken
   zusammenfassen.
4. Keine Dateien verändern, außer der Nutzer bittet ausdrücklich darum.

### `state save` / `save`

1. `state.md` vollständig auf Basis des aktuellen Gesprächsstands aktualisieren.
2. Alle Felder der Mindeststruktur beibehalten.
3. Keine erneute Quellenprüfung, kein History-Eintrag und keine Distribution.
4. Die Struktur von `03_work/` kurz prüfen und bei erkennbarem Bedarf einen
   konkreten, optionalen Verbesserungsvorschlag nennen.
5. Danach kurz den gesicherten Stand, offene Fragen, Risiken, Strukturhinweis
   und nächsten Schritt wiedergeben.

### `update` / `update sources`

1. Zuerst das Context-Restore-Gate vollständig ausführen.
2. `state.md` und `02_context/source-index.md` lesen.
3. `01_sources/` inventarisieren und neue, veränderte oder nicht erfasste
   Quellen feststellen.
4. Quellenindex aktualisieren, ohne neue Quellen automatisch zu ingestieren.
5. Ingestion-Auswahl und Reihenfolge vorschlagen.
6. Nur freigegebene oder eindeutig beauftragte Quellen auswerten.
7. Status und Umfang pro Quelle dokumentieren.
8. Kontext, Arbeitsdateien, Referenzen, Annahmen, Entscheidungen und offene
   Fragen gegen den neuen Stand prüfen.
9. Widersprüche lösen oder dokumentieren.
10. `state.md` aktualisieren.
11. `04_dist/` unverändert lassen; Distribution erst nach Abstimmung vorschlagen.

### `close` / `session close`

1. `state.md`, aktive Dateien und relevante Quellenreferenzen prüfen.
2. Aktuellen Stand, Entscheidungen, Annahmen, offene Fragen und Risiken sichern.
3. `state.md` vollständig aktualisieren.
4. Bei substanziellem Fortschritt seit dem letzten History-Eintrag eine
   History-Datei nach dem oben beschriebenen Format anlegen.
5. Quellen- und Ingestion-Stand sowie nicht erledigte Punkte prüfen.
6. Distributionsfähige Ergebnisse und konkrete Optionen nennen, aber nichts
   ohne Zustimmung nach `04_dist/` kopieren oder dort überschreiben.
7. Wenn ein Git-Repo und ein neuer History-Eintrag vorliegen, eine kurze
   Ein-Zeilen-Headline aus `Completed` ausgeben.
8. Kurz berichten: Erledigtes, gültige Entscheidungen, offene Fragen und
   Risiken, nicht ausgewertete Quellen sowie nächsten sinnvollen Schritt.
9. Diese Abschlusszusammenfassung auch ausgeben, wenn kein History-Eintrag
   angelegt wurde.

### `update template` / `update project-template`

Vor Ausführung `UPDATE.md` vollständig lesen und befolgen. Ohne dort geforderte
Zustimmung keine Template-Dateien, Remotes oder `.template-version` verändern.
`README.md` bleibt projektspezifisch und wird durch diesen Befehl nicht
übernommen. `01_sources/`, `02_context/`, `03_work/` und `04_dist/` bleiben
unverändert.

### `set vault-mode obsidian|plain`

`.vault-mode` mit dem gewünschten Wert schreiben. Beim Wechsel zu `obsidian`
die Setup-Schritte aus `INIT.md` verwenden; bestehende Inhalte nicht
rückwirkend konvertieren. Beim Wechsel zu `plain` bestehende `.obsidian/`
Konfiguration nicht automatisch entfernen.

## Zustimmung und Sicherheit

Vor destruktiven, schwer reversiblen oder extern wirksamen Aktionen Ziel und
Umfang prüfen und ausdrückliche Zustimmung einholen. Dazu gehören insbesondere
Git-Historie löschen, Remotes ändern, Dateien unter `01_sources/` verändern,
Dateien unter `04_dist/` überschreiben und externe Nachrichten oder ähnliche
Aktionen senden.
