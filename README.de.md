# lx-skill

<!-- i18n-source-sha256: 1eae846e141bad0ec5da0191dc1dc627e060b1db85429d254e5947dacdab8a92 -->

[简体中文](README.md) | [English](README.en.md) | [Español](README.es.md) | Deutsch | [日本語](README.ja.md) | [한국어](README.ko.md)

`lx-skill` ist eine wachsende Sammlung von Agent Skills für KI-Bildung, Bildung im neuen Zeitalter, digitale Bildung und persönliche Entwicklung. Sie bündelt Li Xiangs Erfahrungen aus ländlicher Bildungsarbeit, KI-gestütztem Lernen und Kommunikation in hierarchischen Organisationen. Die Skills funktionieren mit Codex, Claude Code und anderen Agenten, die die offene Agent-Skills-Spezifikation unterstützen.

## Enthaltene Skills

| Skill | Geeignet für |
| --- | --- |
| `lx-education-diagnosis` | Ganzheitliche Bildungsdiagnose sowie die Reflexion konkreter Erziehungs- oder Unterrichtsentscheidungen |
| `lx-parent-learning-environment` | Hausaufgabenroutinen, Ermahnen, Vergleiche, Bildschirmkonflikte, unklare Aufgaben und unpassende Schwierigkeit |
| `lx-ai-learning-coach` | Zielklärung, jeweils eine Leitfrage, abgestufte Hinweise, Übung, Erklären in eigenen Worten und projektbasiertes Lernen |
| `lx-institutional-social-coach` | Kommunikation nach oben, Grenzen im Kollegium, informelle Termine, Büropolitik und soziale Anspannung in hierarchischen Organisationen |

Die Skills antworten in der Sprache der Nutzerinnen und Nutzer. Die eigentliche Logik bleibt in einer gemeinsamen Version, damit Übersetzungen nicht auseinanderlaufen.

## Grundsätze

- Systeme und beobachtbares Verhalten untersuchen, nicht Persönlichkeiten diagnostizieren.
- Autonomie, Neugier, Urteilsfähigkeit und nachhaltige Anstrengung schützen.
- KI für Fragen, Hinweise, Simulation und Feedback einsetzen, nicht als standardmäßigen Ersatz für eigenes Denken.
- Erst die Fakten rekonstruieren, dann urteilen oder ein umkehrbares Experiment vorschlagen.
- Machtunterschiede realistisch berücksichtigen und zugleich Würde, Sicherheit und Regelkonformität wahren.
- Keine psychologischen oder medizinischen Diagnosen und keine Beschämung, Angst oder Etikettierung.

## Beispiele

```text
Nutze $lx-education-diagnosis im Modus für Bildungsentscheidungen und Ereignisreflexion.
Ich habe mein Kind heute angeschrien. Frage zuerst nach dem vollständigen Ablauf und hilf mir danach bei der Wiedergutmachung.
```

```text
Nutze $lx-ai-learning-coach, um mir SQL durch angeleitete Übungen beizubringen.
Stelle jeweils nur eine zentrale Frage und verrate die Endlösung nicht sofort.
```

```text
Nutze $lx-institutional-social-coach, um ein Statusgespräch mit meiner Führungskraft vorzubereiten.
Trenne Fakten, Deutungen, formale Risiken und kontrollierbare Schritte und formuliere ein Gesprächsskript.
```

## Herunterladen

```bash
git clone https://github.com/lxqq66/lx-skill.git
cd lx-skill
```

Jeder kann dieses öffentliche Repository ansehen und herunterladen. Ohne Schreibberechtigung kann niemand das Original direkt ändern. Forks und Pull Requests verändern das Original erst, wenn der Eigentümer sie übernimmt.

## Installation für Codex

```bash
mkdir -p ~/.agents/skills
cp -R skills/lx-* ~/.agents/skills/
```

Für ein einzelnes Projekt werden die Ordner nach `.agents/skills/` kopiert. Expliziter Aufruf:

```text
$lx-education-diagnosis
$lx-parent-learning-environment
$lx-ai-learning-coach
$lx-institutional-social-coach
```

## Installation für Claude Code

```bash
mkdir -p ~/.claude/skills
cp -R skills/lx-* ~/.claude/skills/
```

Für ein einzelnes Projekt werden die Ordner nach `.claude/skills/` kopiert. Expliziter Aufruf:

```text
/lx-education-diagnosis
/lx-parent-learning-environment
/lx-ai-learning-coach
/lx-institutional-social-coach
```

## Übersetzungen synchron halten

Die chinesische `README.md` ist die Dokumentationsquelle. Nachdem eine Änderung in alle sechs README-Dateien übertragen wurde, ausführen:

```bash
python3 scripts/check_i18n_sync.py --update-markers
python3 scripts/check_i18n_sync.py
```

Eine GitHub Action führt dieselbe Prüfung für relevante Änderungen aus. Einzelheiten stehen in [docs/i18n-maintenance.md](docs/i18n-maintenance.md).

## Struktur und Sicherheit

Jeder Ordner unter `skills/` ist eigenständig installierbar und enthält eine standardisierte `SKILL.md`, optionale Codex-Metadaten in `agents/openai.yaml` sowie schrittweise geladene Referenzen. Siehe die [Agent-Skills-Spezifikation](https://agentskills.io/specification) und die [Roadmap](ROADMAP.md).

Dieses Projekt unterstützt Bildungsreflexion, Lernen, Gesprächsvorbereitung und kleine Handlungsexperimente. Es ersetzt keine psychologische, medizinische, rechtliche oder Notfallhilfe. Übermittle einer KI keine echten Namen, Schul- oder Arbeitgeberdaten, Adressen, Kontaktdaten, vertraulichen Dokumente oder andere unnötige personenbezogene Informationen.
