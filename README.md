# Wissensprojekt

Dieses Projekt unterstützt dich dabei, aus Quellen belastbare Erkenntnisse und fertige Ergebnisse zu entwickeln.

## So ist das Projekt aufgebaut

```text
01_sources/   Unveränderte Quellen
02_work/      Analysen, Entwürfe und Arbeitsstände
03_dist/      Fertige, freigegebene Ergebnisse
```

Quellen unter `01_sources/` werden niemals verändert.

Arbeitsstände entstehen unter `02_work/`. Fertige Ergebnisse werden erst nach deiner Zustimmung nach `03_dist/` kopiert.

## So arbeitest du damit

Du kannst:

* neue Quellen unter `01_sources/` bereitstellen,
* Fragen zu den Quellen stellen,
* Analysen oder Ergebnisse beauftragen,
* den Fokus und die Prioritäten ändern,
* Arbeitsstände prüfen und fortsetzen.

Der Agent übernimmt:

* Quellen lesen und referenzieren,
* Wissen strukturieren und verdichten,
* Annahmen, Interpretationen und Fakten trennen,
* Widersprüche und offene Fragen dokumentieren,
* Arbeitsstände unter `02_work/` pflegen,
* distributionsfähige Ergebnisse vorschlagen.

## Wichtige Befehle

### Projektstand anzeigen

```text
project status
```

Auch natürliche Formulierungen funktionieren:

```text
Wo stehen wir?
Was ist aktuell offen?
Was sind die nächsten Schritte?
```

### Wissen und Arbeitsstände aktualisieren

```text
project update
```

Der Agent prüft neue oder veränderte Quellen, aktualisiert Analysen und dokumentiert Auswirkungen.

### Arbeit für heute abschließen

```text
project close
```

Der Agent hält den aktuellen Stand, Entscheidungen, offene Fragen und nächste Schritte fest.

Fertige Ergebnisse werden dabei nur vorgeschlagen. Das Kopieren nach `03_dist/` erfolgt erst nach deiner Zustimmung.

## Typischer Ablauf

1. Quellen unter `01_sources/` ablegen.
2. Ziel oder Frage formulieren.
3. Agent analysiert und arbeitet unter `02_work/`.
4. Zwischendurch mit `project status` den Stand prüfen.
5. Fertiges Ergebnis prüfen und für `03_dist/` freigeben.
6. Mit `project close` einen belastbaren Wiedereinstiegspunkt erzeugen.

Du musst die Befehle nicht exakt verwenden. Normale Sprache reicht.
