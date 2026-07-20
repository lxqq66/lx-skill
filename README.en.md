# lx-skill

English | [简体中文](README.md)

`lx-skill` is a growing Agent Skills collection for AI education, education in the new era, digital education, and personal growth. It distills Li Xiang's experience in rural education, AI-supported teaching, and communication inside hierarchical organizations. The skills work with Codex, Claude Code, and other agents that support the open Agent Skills specification.

## Included skills

| Skill | Use it for |
| --- | --- |
| `lx-education-diagnosis` | Whole-system education diagnosis and a dedicated decision/event review mode for parenting or teaching choices |
| `lx-parent-learning-environment` | Homework prompting, comparisons, screen conflict, unclear tasks, difficulty mismatch, feedback, and household rules |
| `lx-ai-learning-coach` | Goal clarification, one-question-at-a-time tutoring, graduated hints, practice, teach-back, and project learning |
| `lx-institutional-social-coach` | Managing up, workplace boundaries, informal gatherings, office politics, and social anxiety in hierarchical organizations |

All skills follow the user's language and support both English and Simplified Chinese.

## Core principles

- Diagnose systems and observable actions, not personalities.
- Protect autonomy, curiosity, judgment, and sustainable effort.
- Use AI for questions, hints, feedback, and simulation instead of default answer substitution.
- Reconstruct the facts before offering a judgment, script, or reversible experiment.
- Recognize incentives and power differences while preserving dignity, safety, and compliance.
- Do not provide psychological or medical diagnoses or use shame, fear, or labels.

## Download

```bash
git clone https://github.com/lxqq66/lx-skill.git
cd lx-skill
```

Anyone can view and download this public repository. Other users cannot directly change it unless the owner grants them write access. They may modify their own forks or propose a Pull Request, but only the owner or authorized collaborators can merge changes into this repository.

## Install for Codex

```bash
mkdir -p ~/.agents/skills
cp -R skills/lx-* ~/.agents/skills/
```

For a single project, copy them to `.agents/skills/`. Invoke them explicitly with:

```text
$lx-education-diagnosis
$lx-parent-learning-environment
$lx-ai-learning-coach
$lx-institutional-social-coach
```

## Install for Claude Code

```bash
mkdir -p ~/.claude/skills
cp -R skills/lx-* ~/.claude/skills/
```

For a single project, copy them to `.claude/skills/`. Invoke them explicitly with:

```text
/lx-education-diagnosis
/lx-parent-learning-environment
/lx-ai-learning-coach
/lx-institutional-social-coach
```

## Examples

```text
Use $lx-education-diagnosis in education decision and event review mode. I yelled at my child today. Ask for the full sequence before judging it, then help me repair it.
```

```text
Use $lx-ai-learning-coach to teach me SQL through guided practice. Ask one core question at a time and do not reveal the final answer immediately.
```

```text
Use $lx-institutional-social-coach to prepare a progress update for my manager. Separate facts, interpretations, formal risks, and controllable actions, then draft a script.
```

## Repository structure

Each folder under `skills/` is independently installable and includes a standard `SKILL.md`, optional Codex interface metadata in `agents/openai.yaml`, and progressively loaded references. See the [Agent Skills specification](https://agentskills.io/specification), [OpenAI Codex Skills documentation](https://developers.openai.com/codex/skills), and [Claude Code Skills documentation](https://code.claude.com/docs/en/skills).

Use [tests/evaluation-cases.md](tests/evaluation-cases.md) for manual regression testing after changes. Future skills are listed in [ROADMAP.md](ROADMAP.md).

## Safety and privacy

This project offers educational reflection, learning support, communication preparation, and small action experiments. It does not replace mental-health, medical, legal, or emergency services.

Do not send an AI real names, school or employer details, home addresses, contact information, confidential documents, classified information, or other unnecessary personal data.
