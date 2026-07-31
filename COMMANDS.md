# Alle wichtigen Befehle

> Diese Datei wird vom Template [`agentic-project-template`](https://github.com/ag-constructiva/agentic-project-template) verwaltet und bei `update template` mitsynchronisiert. Vollständige Ablauflogik siehe [AGENTS.md](AGENTS.md).

Du musst die Befehle nicht exakt verwenden. Normale Sprache reicht.

### Sitzung starten

```text
session start
start
starten
los geht's
los
```

Der richtige erste Befehl in jeder Sitzung — auch der allerersten. Beim allerersten Mal klärt der Agent gemeinsam mit dir den Projektauftrag und legt die Startdateien an. Bei jedem weiteren Einstieg fasst er den aktuellen Stand zusammen und weist auf neue, noch nicht ausgewertete Quellen hin.

### Projektstand anzeigen

```text
status
```

Auch natürliche Formulierungen funktionieren:

```text
Wo stehen wir?
Was ist aktuell offen?
Was sind die nächsten Schritte?
```

### Wissen und Arbeitsstände aktualisieren

```text
update
update sources
```

Der Agent prüft neue oder veränderte Quellen, aktualisiert Analysen und dokumentiert Auswirkungen.

### Zwischenstand sichern

```text
state save
save
Halte den Zwischenstand fest.
```

Schreibt den im Gespräch gehaltenen Zwischenstand sofort nach `02_work/state.md`, ohne die übrigen Schritte von `close` — kein History-Eintrag, keine erneute Quellenprüfung. Sinnvoll als Absicherung während einer längeren Sitzung, wenn noch kein `close` ansteht.

### Arbeit für heute abschließen

```text
session close
close
```

Der Agent hält den aktuellen Stand, Entscheidungen, offene Fragen und nächste Schritte fest.

Fertige Ergebnisse werden dabei nur vorgeschlagen. Das Kopieren nach `03_dist/` erfolgt erst nach deiner Zustimmung.

### Projekt-Template aktualisieren

```text
update template
update project-template
```

Prüft, ob für das öffentliche Template [`agentic-project-template`](https://github.com/ag-constructiva/agentic-project-template) eine neuere Version vorliegt, zeigt relevante Änderungen aus dessen Changelog und übernimmt sie erst nach deiner Zustimmung — Datei für Datei, unter Erhalt deiner lokalen Anpassungen.
