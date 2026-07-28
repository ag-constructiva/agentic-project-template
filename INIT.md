# Projekt-Ersteinrichtung — Agentenprotokoll

> **Hinweis:** Diese Datei enthält ausschließlich Ablaufanweisungen für den Agenten zur Ersteinrichtung eines neuen Projekts — Ausführung nur beim allerersten `project start`, wenn `02_work/state.md` noch nicht existiert. Wird nur bei diesem Erststart gelesen. Für alle übrigen Arbeitsregeln siehe [AGENTS.md](AGENTS.md).

## Projektstart klären

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

Struktur von `state.md`: siehe Abschnitt `Arbeitszustand` in [AGENTS.md](AGENTS.md).

## Ablauf Erststart

1. Klärung mit Nutzer gemäß Abschnitt `Projektstart klären` oben (Ziel, Ergebnisse, Zielgruppe, Erfolg, Kontext und Grenzen, Ausgangslage, Startbereitschaft).
2. Auf Antwort-Basis `02_work/project-brief.md` und `02_work/state.md` anlegen.
3. `README.md` im Projektwurzelverzeichnis aktualisieren: konkretes Projekt beschreiben (Zweck, Zielgruppe, angestrebte Ergebnisse) statt generischer Vorlagenbeschreibung. Abschnitte zu Projektstruktur/Befehlen inhaltlich erhalten.
4. Prüfen, ob `.template-version` existiert. Falls nicht: fragen, ob Projekt mit öffentlichem Template aktuell gehalten werden soll (Verknüpfung mit `https://github.com/ag-constructiva/agentic-project-template`). Nach Zustimmung `.template-version` anlegen — Vorgehen wie [UPDATE.md](UPDATE.md), Schritt 2b.
5. Konkreter Vorschlag für nächsten Schritt → auf Bestätigung warten → erst danach Quellen ingestieren oder größere Arbeitsstrukturen anlegen.
