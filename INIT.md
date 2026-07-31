# Projekt-Ersteinrichtung — Agentenprotokoll

> **Hinweis:** Diese Datei enthält nur Ablaufanweisungen für den Agenten zur Ersteinrichtung eines neuen Projekts. Wird nur beim allerersten `start` gelesen, wenn `02_work/state.md` noch nicht existiert. Für alle übrigen Arbeitsregeln siehe [AGENTS.md](AGENTS.md).

## Git-Herkunft prüfen

Vor Arbeitsbeginn: ist das Projektverzeichnis noch git-technisch mit dem öffentlichen Template `agentic-project-template` verbunden (typischer Fall bei Ordner-Kopie oder `git clone` statt GitHubs „Use this template"-Button)?

1. Ist das Verzeichnis kein Git-Repo → kein Problem, weiter mit `Projektstart klären`.
2. Ist es ein Git-Repo: `git remote -v` prüfen (zeigt ein Remote auf `ag-constructiva/agentic-project-template`?) und ersten Commit prüfen (`git log --reverse --oneline | head -1`, bekannter Template-Seed-Commit z. B. „initial commit as v1"). Trifft eines zu → Verbindung zum Template liegt vor.
3. Liegt eine Verbindung vor, Nutzer aktiv informieren und Fix anbieten, differenziert nach Fall:
   * **Keine projekteigenen Commits vorhanden** (Historie besteht ausschließlich aus Template-Commits): nach ausdrücklicher Zustimmung vollständigen Reset anbieten (`git remote remove origin`, `rm -rf .git`, `git init`, initialer Commit des aktuellen Stands).
   * **Es existieren bereits projekteigene Commits** oberhalb der Template-Historie: Historie nicht blind verwerfen (Datenverlust-Risiko) — stattdessen nur Remote-Entkopplung anbieten (`git remote remove origin`, ggf. neuen eigenen Remote einrichten), Historie bleibt erhalten. Ausdrücklich auf die verbleibende geteilte Vorgeschichte hinweisen.
   * In beiden Fällen: Aktion nur nach expliziter Nutzer-Zustimmung, keine automatische Ausführung.
4. Ohne Zustimmung: keine Git-Operation ausführen, Hinweis unter `Next Actions` in `state.md` festhalten, sobald diese existiert.

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

1. Git-Herkunft prüfen gemäß Abschnitt `Git-Herkunft prüfen` oben.
2. Klärung mit Nutzer gemäß Abschnitt `Projektstart klären` oben (Ziel, Ergebnisse, Zielgruppe, Erfolg, Kontext und Grenzen, Ausgangslage, Startbereitschaft).
3. Auf Antwort-Basis `02_work/project-brief.md` und `02_work/state.md` anlegen.
4. `README.md` im Projektwurzelverzeichnis aktualisieren: konkretes Projekt beschreiben (Zweck, Zielgruppe, angestrebte Ergebnisse) statt generischer Vorlagenbeschreibung. Abschnitt zur Projektstruktur inhaltlich erhalten. `COMMANDS.md` bleibt unverändert — sie ist eine vom Template verwaltete Datei, kein Bestandteil der Projektanpassung.
5. Existiert `.template-version`? Falls nicht: fragen, ob Projekt mit öffentlichem Template aktuell gehalten werden soll (Verknüpfung mit `https://github.com/ag-constructiva/agentic-project-template`). Nach Zustimmung `.template-version` anlegen — Vorgehen wie [UPDATE.md](UPDATE.md), Schritt 2b.
6. Konkreter Vorschlag für nächsten Schritt → auf Bestätigung warten → erst danach Quellen ingestieren oder größere Arbeitsstrukturen anlegen.
