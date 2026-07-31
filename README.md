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

## Getting started

1. Neues Projekt über den Button **„Use this template"** auf [github.com/ag-constructiva/agentic-project-template](https://github.com/ag-constructiva/agentic-project-template) erzeugen — liefert ein eigenständiges Repo ohne geteilte Git-Historie. (Alternative: Ordner kopieren oder klonen — der Agent prüft das beim ersten `start` und bietet an, die Git-Anbindung ans Template zu lösen.)
2. Optional: Erste Quellen oder Notizen unter `01_sources/` ablegen.
3. Gib deinem Agenten den Befehl `start` — beim allerersten Mal entsteht dabei der Projektauftrag.
4. Arbeite mit deinem Agenten, wie es dir beliebt. Steig in jede weitere Sitzung wieder mit `start` ein.
5. Wenn du unterbrechen willst, gib den Befehl `close`, dann kannst du später dort wieder ansetzen.

### Optional: Obsidian-Vault

Optional kannst du das Projekt auch als Obsidian-Vault nutzen. Der Modus wird beim ersten Start erfragt und lässt sich später mit `set vault-mode obsidian`/`set vault-mode plain` wechseln. Öffne danach einfach den Projektordner in Obsidian als Vault.

## Verfügbare Befehle

| Befehl | Zweck |
|---|---|
| `start` | Sitzung beginnen — beim allerersten Mal Projekt einrichten, danach Stand zusammenfassen |
| `status` | Aktuellen Stand anzeigen |
| `update` | Quellen und Arbeitsstände prüfen/aktualisieren |
| `state save` | Zwischenstand sofort sichern |
| `close` | Sitzung abschließen, Wiedereinstieg vorbereiten |
| `update template` | Projekt-Template auf neue Version prüfen und aktualisieren |
| `set vault-mode obsidian`/`plain` | Zwischen Obsidian-Vault und Editor-/IDE-Modus wechseln |

Du musst die Befehle nicht exakt verwenden. Normale Sprache reicht. Mehr Infos zu Ablauf und Hintergrund der einzelnen Befehle: [AGENTS.md](AGENTS.md), Abschnitt „User Commands".

## Typischer Ablauf

1. Mit `start` beginnen — beim allerersten Mal entsteht dabei der Projektauftrag.
2. Quellen unter `01_sources/` ablegen.
3. Ziel oder Frage formulieren.
4. Agent analysiert und arbeitet unter `02_work/`.
5. Zwischendurch den aktuellen Stand mit `save` speichern oder mit `status` den Stand prüfen.
6. Erarbeitete Ergebnisse prüfen und für `03_dist/` freigeben.
7. Mit `close` einen belastbaren Wiedereinstiegspunkt erzeugen, in der nächsten Sitzung mit `start` wieder einsteigen.
