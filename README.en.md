# 🎬 AI Drama Production

> **From a rough idea to a production-ready AI video plan with copy-paste prompts.**

<p align="center">
  <a href="README.md">🇨🇳 中文版</a> &nbsp;|&nbsp;
  <a href="./SKILL.md">📖 Skill Manifest</a> &nbsp;|&nbsp;
  <a href="./references/workflow.md">🎬 Film Pipeline Workflow</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/platform-Claude%20Code-8A2BE2" alt="Claude Code">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT License">
  <img src="https://img.shields.io/badge/AI%20short%20film-ready-success" alt="AI Short Film Ready">
  <img src="https://img.shields.io/badge/copy--paste%20prompt%20pack-default-success" alt="Copy Paste Prompt Pack">
</p>

---

## 🎯 What Is This?

**AI Drama Production** is a [Claude Code](https://docs.anthropic.com/en/docs/claude-code/skills) skill that turns a rough creative idea into a complete AI drama, AI short film, trailer, anime image-to-video, or light still-image motion production plan.

It does not generate the video itself. It generates the **production blueprint**: script, storyboard, reference image prompts, start/end keyframe prompts, video prompts, bridge shots, safety inserts, repair prompts, sound design, continuity planning, and editing guidance. The user can focus on the idea and review; the skill handles prompts, settings, continuity, and repair plans.

---

## 🎬 One Entry: Film Pipeline

| Capability | Best For | Output |
|---|---|---|
| **Film Mode** | Cinematic AI shorts, drama episodes, trailers, contests, anime image-to-video, still-image light motion | Storyboard, Join Contracts, keyframes, video prompts, bridge shots, safety inserts, repair prompts |
| **Copy-Paste Prompt Pack** | Users who want to provide ideas and review choices while the skill handles prompting and repairs | `IMAGE_START` / `IMAGE_END` / `IMAGE_MID` / `VIDEO_MAIN` / `VIDEO_BRIDGE` / `VIDEO_INSERT` / `VIDEO_REPAIR` |
| **Anime Light-Motion Variant** | Existing anime images that only need push-ins, pans, light expression/environment motion, or editing keyframes | Still uses film mode, with gentler camera movement, shorter action beats, and stronger reference locking |

> Voiceover-driven stills, anime light motion, and static-image animation all use the film pipeline with reduced motion complexity.

---

## ✨ Why This Skill?

Most AI video projects fail before generation: the shot design, continuity, prompt structure, and repair plan are incomplete.

This skill solves four real problems:

1. **No clear starting point** — Intake, foundations, script discussion, director analysis, storyboard, and prompt pack are generated in one workflow.
2. **Character drift** — Character, scene, and prop references are designed before video prompts; every visual noun must trace back to an `@图片` or `@视频` reference.
3. **Broken cuts** — `Join Contract` tables audit every adjacent shot pair: prior end state, next start state, state delta, risk level, hard-cut permission, bridge shot, sound bridge, and fallback edit.
4. **No repair path after generation fails** — Risky shots ship with bridge, insert, and repair prompts so the user can retry by copy-paste instead of inventing fixes mid-edit.

---

## 🚀 Features

| Feature | What It Does |
|---|---|
| **Low-input defaults** | Asks at most for genre, protagonist relationship, first hook, ending question, and target platform |
| **Multi-agent script development** | 3-5 rounds of critique from writer, director, audience, and compliance perspectives |
| **Director analysis** | Converts abstract emotion into concrete action, camera, light, sound, and edit points |
| **Reference-first design** | Character, scene, and prop prompts come before video prompts |
| **Join Contract** | Every adjacent shot pair has a continuity contract; risky hard cuts are blocked |
| **Automatic bridge generation** | Location changes, carry/rescue actions, posture jumps, body interaction, and prop-state changes get `VIDEO_BRIDGE` or `VIDEO_INSERT` prompts |
| **Copy-paste prompt pack** | Each shot receives ready-to-use keyframe, video, bridge, insert, and repair prompts |
| **Inline sound** | Video prompts embed `[对白]`, `[音效]`, and `[配乐]`; no `@音频` references |
| **Still rough cut first** | Start/end frames are assembled before video generation to audit timing, composition, posture, location, and dialogue duration |
| **Post-generation repair loop** | After clips are generated, the skill reviews broken joins and outputs replacement bridge/insert prompts plus edit decisions |

---

## 📦 Output Contract

```text
📄 Production Bible
├── 📋 Project Brief & Creative Direction
├── 🌍 Worldbuilding, Theme & Story Structure
├── 📝 Multi-Agent Script Iteration Log (3+ rounds)
├── 👤 Character Bible (visual design + reference prompts)
├── 🏠 Scene / Location / Prop Bible
├── 🎨 Style Bible (color, lighting, lens, rhythm, sound, forbidden drift)
├── 🎬 Director Analysis
├── 📊 Storyboard Table
├── 🔗 Continuity Plan + Join Contracts
├── 🖼️ Start/End Keyframe Rough-Cut Plan
├── 📋 Copy-Paste Prompt Pack
│   ├── IMAGE_START / IMAGE_END / IMAGE_MID
│   ├── VIDEO_MAIN / VIDEO_BRIDGE
│   └── VIDEO_INSERT / VIDEO_REPAIR
├── 🧩 Safety Insert Library
├── 🖼️ Cover / Thumbnail Design
└── ✅ Review Gates & Repair Plan
```

---

## ⚡ Quick Start

```bash
git clone https://github.com/Amouren7/ai-drama-production.git \
  ~/.claude/skills/ai-drama-production
```

Invoke in Claude Code:

```text
/ai-drama-production I want to make a cyberpunk AI short film
```

Bring a premise, target platform, duration, and reference images if you have them. If not, the skill fills sensible defaults.

---

## 🔄 Workflow

```text
💡 Intake
  → 🏗️ Four Foundations (World / Character / Story / Style)
  → 📝 Multi-Agent Script Development
  → 🎬 Director Analysis
  → 📊 Storyboard + Join Contracts + High-Risk Bridges
  → 🖼️ Start/End Keyframe Rough Cut
  → 📋 Copy-Paste Prompt Pack
  → 🎥 Video Generation Batches
  → 🧩 Safety Inserts / Repair Prompts
  → 🔊 Sound & Editing
  → ✅ Review & Repair
```

---

## 📂 Project Structure

```text
ai-drama-production/
├── SKILL.md                          # Skill manifest, entry point, core rules
├── agents/
│   └── openai.yaml                   # Agent configuration
├── references/
│   ├── workflow.md                   # Film pipeline workflow
│   ├── templates.md                  # Templates and Markdown skeleton
│   ├── production-practice.md        # Tactical lessons from finished productions
│   └── review-checklists.md          # Scoring gates and repair strategies
├── README.md                         # Default: Chinese
├── README.en.md                      # English
└── LICENSE
```

---

## 🔧 Toolchain

| Tool | Use |
|---|---|
| **Seedance / 即梦 / other image-to-video tools** | Generate main shots, bridge shots, and inserts |
| **Image generation or image editing tools** | Create characters, scenes, props, and start/end keyframes |
| **剪映 / Premiere Pro / any NLE** | Still rough cut, assembly, subtitles, sound, repair edits |
| **TTS or human recording** | Scratch voice for timing, final voice after picture timing is stable |
| **Claude Code** | Run the skill and generate the full Markdown plan |

> The generated Markdown is standalone. You can follow the prompts, assembly guide, and review checklist without running the skill again.

---

## 🧠 Design Principles

| Principle | Why It Matters |
|---|---|
| **Story first** | Premise, conflict, and emotion drive retention |
| **Lock references before video prompts** | Character, scene, and prop consistency must be designed up front |
| **Rough cut before video generation** | Still-image rough cuts catch broken timing and composition cheaply |
| **Audit joins before generation** | AI clips are memoryless; adjacent shots must be designed explicitly |
| **No high-risk hard cuts** | Location, posture, prop, and body-interaction changes need bridges or inserts |
| **Sound belongs inside prompts** | Dialogue, SFX, ambience, and music drive edit rhythm |
| **Failures must be repairable** | Risky shots need repair prompts and fallback edits |

---

## 🤝 Contributing

- Found a gap? Open an issue or PR.
- Have a production postmortem? Add it to `references/production-practice.md`.
- Want to change a rule? Include a failure case or production rationale.

---

## 📄 License

MIT — use it, fork it, build on it.

---

<p align="center">
  Made for AI video creators
</p>
