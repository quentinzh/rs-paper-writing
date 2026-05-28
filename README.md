# Skills: Recommender Systems Paper Writing

[English](./README.md) | [中文](./README_zh.md)

This repository provides one Codex skill for writing and revising recommender-system research papers.

The skill is adapted for papers targeting venues such as KDD, SIGIR, WWW, AAAI, ACL, RecSys, CIKM, and WSDM. It covers general recommender-system writing as well as LLM-based recommendation, fairness/debiasing/causal recommendation, sequential recommendation, retrieval, ranking, and evaluation-focused revision.

## Attribution

Most writing principles and methodology in this repository are inspired by Prof. Peng Sida's open study notes:

- https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e
- Prof. Peng's original repository: https://github.com/pengsida/learning_research

This repository is also adapted from and acknowledges the project:

- https://github.com/Master-cai/Research-Paper-Writing-Skills/tree/main

My contribution is the recommender-system adaptation, content restructuring, and packaging as a reusable skill.

## Repository Overview

This repository currently provides one skill package:

- `rs-paper-writing/`
  - `SKILL.md`: core workflow and usage rules
  - `references/`: section-specific writing guides and templates
  - `agents/openai.yaml`: agent metadata

Typical use cases:

- Drafting or revising Abstract, Introduction, Preliminary, Method, Experiments, Related Work, and Conclusion
- Improving section logic, paragraph flow, and reviewer-facing clarity
- Checking claim-evidence alignment
- Reviewing metrics, baselines, significance, efficiency, LLM generation validity, grounding, and fairness/accuracy trade-offs
- Running pre-submission self-review from a skeptical recommender-system reviewer perspective

## Installation

Assume you are in the repository root.

### 1. Codex

Copy the skill into `$CODEX_HOME/skills/`:

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R rs-paper-writing "$CODEX_HOME/skills/"
```

Usage example:

```text
Use $rs-paper-writing to improve my recommender-system paper's Introduction.
```

### 2. Claude Code

Use either a global or project-level installation.

Global:

```bash
mkdir -p "$HOME/.claude/skills"
cp -R rs-paper-writing "$HOME/.claude/skills/"
```

Project-level:

```bash
mkdir -p .claude/skills
cp -R rs-paper-writing .claude/skills/
```

In prompts, explicitly request this skill, for example:

```text
Please use the rs-paper-writing skill.
```

### 3. Gemini

Copy this skill into your Gemini skills directory:

```bash
mkdir -p "$HOME/.gemini/skills"
cp -R rs-paper-writing "$HOME/.gemini/skills/"
```

Then ask concrete tasks such as rewriting an Abstract with claim-evidence checks.

## License

See [LICENSE](./LICENSE) for the license terms.
