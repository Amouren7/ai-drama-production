# AI Drama Production

A Claude Code skill for AI drama and motion comic production. Two modes, one workflow:

- **🎬 Film mode** — continuous video generation pipeline for Seedance/即梦, targeting AI short films, trailers, and cinematic sequences
- **🎞️ Motion comic mode** — voiceover-driven, panel-based still-image assembly for 即梦 + 剪映, targeting narrative-driven stories with realistic or sci-fi visual quality

---

## Features

- **Two production modes** — choose film or motion comic at intake; the rest of the workflow adapts
- **Creative layer** — worldbuilding, character bible, scene bible, style bible for both modes
- **Director analysis (讲戏)** — turn abstract emotion into visible action chains (film mode)
- **Voiceover-to-panel mapping** — automatic timing estimation and panel assignment (motion comic)
- **Batch image prompt generation** — style prefix auto-injection, character reference linking
- **Camera motion assignment** — 4 motion types for motion comic, full camera grammar for film
- **剪映 assembly guide** — per-panel duration, keyframe animation, transitions, multi-track layout
- **Review checklists** — 7+ scoring gates with PASS/WARN/FAIL and repair strategies
- **Pure Markdown output** — no backend, no database, no login required

---

## Modes Comparison

| | Film Mode | Motion Comic Mode |
|---|---|---|
| **Best for** | AI short films, trailers, cinematic sequences | Narrative-driven stories, sci-fi/realistic motion comics |
| **Generation type** | Continuous video (4-15s per shot) | Still images assembled with keyframe animation |
| **Toolchain** | Seedance / 即梦 图生视频 | 即梦 出图 + 剪映 装配 |
| **Core output** | Video prompt pack, storyboard table | Panel mapping, batch prompts, assembly guide |
| **Key skill** | Director analysis (讲戏), shot continuity | Voiceover timing, panel pacing, consistency control |
| **Production speed** | Slow: generate per-shot video | Fast: batch image gen + assembly |

---

## Installation

### As a Claude Code skill

```bash
# Clone the repo into your Claude Code skills directory
git clone https://github.com/Amouren7/ai-drama-production.git \
  ~/.claude/skills/ai-drama-production
```

Or copy the `ai-drama-production` directory into `~/.claude/skills/`.

### Standalone usage

The Markdown output from this skill is fully standalone. Once generated, you can use it without Claude Code — just follow the prompts, assembly guides, and workflow instructions directly.

---

## Quick Start

1. In Claude Code, invoke the skill by describing your project:
   ```
   /ai-drama-production 我想做一个赛博朋克题材的AI短片
   ```
2. The skill will ask what mode you want and a few essentials about your project.
3. Follow the generated production guide from concept to final export.

### What to prepare

- A story premise (even 2-3 sentences is enough)
- Reference images if available (character designs, scene references)
- Target platform and approximate length

---

## Workflow Overview

### Film Mode

```
Intake → Four Foundations (World/Character/Story/Style)
      → Director Analysis (讲戏)
      → Storyboard + Seedance Prompt Generation
      → Rough Cut → Iteration → Sound → Final
```

Full workflow: `references/workflow.md`

### Motion Comic Mode

```
Intake → Four Foundations (shared)
      → Voiceover Script + Timing Breakdown
      → Panel Mapping
      → Batch Image Prompt Generation
      → Camera Motion Assignment
      → 剪映 Assembly Guide
      → Sound Plan → Review → Export
```

Full workflow: `references/workflow-motion-comic.md`

---

## File Structure

```
ai-drama-production/
├── SKILL.md                          # Skill manifest, entry point, core rules
├── agents/
│   └── openai.yaml                   # Agent configuration
├── references/
│   ├── workflow.md                   # Film mode workflow
│   ├── workflow-motion-comic.md      # Motion comic mode workflow
│   ├── templates.md                  # Film mode templates
│   ├── templates-motion-comic.md     # Motion comic templates
│   ├── production-practice.md        # Production lessons from real projects
│   └── review-checklists.md          # Review gates and repair strategies
├── README.md
└── LICENSE
```

---

## Toolchain Requirements

### Film Mode

- **Image/video generation:** Seedance 2.0 or 即梦
- **Editing:** 剪映, Premiere Pro, or any non-linear editor

### Motion Comic Mode

- **Image generation:** 即梦 (or compatible image generation tools)
- **Assembly:** 剪映 (keyframe animation, multi-track audio)
- **Voiceover:** 剪映 built-in TTS, third-party TTS, or human recording

---

## Design Principles

- **Story first.** Spend more effort on premise, conflict, and emotion than on tool trivia.
- **Consistency by design.** Lock character and scene references before generating prompts.
- **Rough cut before final.** Still-image rough cuts catch timing and composition problems cheaply.
- **Sound is storytelling.** Voiceover, ambience, effects, and music each serve a distinct narrative function.
- **Output is production-ready.** Every generated document is a complete guide from assets to assembly.

---

## License

MIT

---

## Related

- [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills)
- [Seedance](https://seedance.com)
- [即梦](https://jimeng.jianying.com)
