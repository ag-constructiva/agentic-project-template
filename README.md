# Wissensprojekt

Dieses Projekt ist eine dateibasierte Workbench für umfangreichere Wissensarbeit mit LLMs und Agenten.

Sie hilft dir dabei, viele heterogene, teilweise widersprüchliche und unterschiedlich vertrauenswürdige Quellen kontrolliert in einen belastbaren Arbeitskontext zu überführen. Daraus entwickelst du schrittweise Arbeitsergebnisse und schließlich nutzbare Ergebnisse für einen konkreten Zweck.

Der grundlegende Ablauf ist:

```text
Quellen → Bewertung und Metadaten → kontrollierte Ingestion
→ verdichteter Wissensstand → Arbeitsprozess → nutzbare Ergebnisse
```

Der Unterschied zu einem gewöhnlichen Chat- oder Projektordner liegt nicht nur darin, dass Dateien dauerhaft vorliegen. Herkunft, Auswahl und Vertrauenswürdigkeit der Quellen bleiben sichtbar. Heterogene, widersprüchliche oder unvollständige Informationen werden nicht unkontrolliert vermischt. Fakten, Interpretationen, Annahmen, Entscheidungen und offene Fragen bleiben unterscheidbar. So kann der Arbeitskontext über Sitzungen, Agenten und Bearbeitungsschritte hinweg nachvollziehbar fortgeführt werden.

Besonders sinnvoll ist diese Workbench, wenn du:

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
02_context/   Verdichteter, wiederverwendbarer Wissenskontext
03_work/      Laufende Fragen, Analysen und Projekte
04_dist/      Fertige, freigegebene Ergebnisse zur Übergabe
```

| Ordner | Zweck |
|---|---|
| `01_sources/` | Unveränderte Primärquellen |
| `02_context/` | Verdichteter, wiederverwendbarer Wissenskontext |
| `03_work/` | Laufende Fragen, Analysen und Projekte |
| `04_dist/` | Freigegebene Ergebnisse zur Übergabe |

Quellen unter `01_sources/` werden niemals verändert.

Der verdichtete Wissenskontext entsteht unter `02_context/`. Laufende Arbeiten entstehen unter `03_work/`. Fertige Ergebnisse werden erst nach deiner Zustimmung nach `04_dist/` kopiert.

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
* Kontext unter `02_context/` und Arbeitsstände unter `03_work/` pflegen,
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
4. Agent verdichtet Wissen unter `02_context/` und arbeitet unter `03_work/`.
5. Zwischendurch den aktuellen Stand mit `save` speichern oder mit `status` den Stand prüfen.
6. Erarbeitete Ergebnisse prüfen und für `04_dist/` freigeben.
7. Mit `close` einen belastbaren Wiedereinstiegspunkt erzeugen, in der nächsten Sitzung mit `start` wieder einsteigen.
