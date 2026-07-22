# Wissensprojekt

Dieses Projekt ist eine Arbeitsvorlage für umfangreichere Wissensarbeit mit LLMs und Agenten.

Es hilft dir dabei, aus Quellen und vorhandenem Kontext schrittweise belastbare Arbeitsergebnisse und daraus fertige, nutzbare Ergebnisse für einen konkreten Zweck zu entwickeln.

Besonders sinnvoll ist diese Struktur, wenn du:

- mit mehreren oder umfangreichen Quellen arbeitest,
- Zwischenergebnisse später weiterverwenden möchtest,
- Erkenntnisse, Annahmen und Entscheidungen nachvollziehbar halten willst,
- über mehrere Sitzungen hinweg an einem Thema arbeitest,
- aus Analyse und Wissensaufbau konkrete Ergebnisse erzeugen möchtest.

Der fachliche Inhalt und der Umfang des Projekts sind offen. Es kann um eine Entscheidung, ein Konzept, eine Recherche, eine Strategie, eine Dokumentation oder ein anderes Ergebnis aus Wissensarbeit gehen.

Damit der Agent sinnvoll arbeiten kann, beschreibst du zu Beginn, worum es in deinem Projekt geht, welchen Zweck es verfolgt und welche Ergebnisse entstehen sollen. Die Projektstruktur sorgt anschließend dafür, dass Quellen, Arbeitsstände und fertige Ergebnisse geordnet, nachvollziehbar und jederzeit wiederaufnehmbar bleiben.

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

### Projekt starten

```text
project start
starten
start
los geht's
los
```

Der einfachste Einstieg in jede Sitzung — immer der richtige erste Befehl. Beim allerersten Start klärt der Agent gemeinsam mit dir den Projektauftrag und legt die Startdateien an. Bei jedem weiteren Einstieg fasst er den aktuellen Stand zusammen und weist auf neue, noch nicht ausgewertete Quellen hin.

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

1. Mit `project start` beginnen — beim ersten Mal entsteht der Projektauftrag, bei jedem weiteren Mal der Wiedereinstieg.
2. Quellen unter `01_sources/` ablegen.
3. Ziel oder Frage formulieren.
4. Agent analysiert und arbeitet unter `02_work/`.
5. Zwischendurch mit `project status` den Stand prüfen.
6. Fertiges Ergebnis prüfen und für `03_dist/` freigeben.
7. Mit `project close` einen belastbaren Wiedereinstiegspunkt erzeugen.

Du musst die Befehle nicht exakt verwenden. Normale Sprache reicht.
