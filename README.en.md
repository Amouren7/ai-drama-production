# 🎬 AI Drama Production

> **From a rough idea to production-ready AI drama — in one Markdown document.**

<p align="center">
  <a href="README.md">🇨🇳 中文版</a> &nbsp;|&nbsp;
  <a href="./SKILL.md">📖 Skill Manifest</a> &nbsp;|&nbsp;
  <a href="./references/workflow.md">🎬 Film Workflow</a> &nbsp;|&nbsp;
  <a href="./references/workflow-motion-comic.md">🎞️ Motion Comic Workflow</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/platform-Claude%20Code-8A2BE2" alt="Claude Code">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT License">
  <img src="https://img.shields.io/badge/AI%20short%20film-ready-success" alt="AI Short Film Ready">
  <img src="https://img.shields.io/badge/motion%20comic-ready-success" alt="Motion Comic Ready">
</p>

---

## 🎯 What Is This?

**AI Drama Production** is a [Claude Code](https://docs.anthropic.com/en/docs/claude-code/skills) skill that turns your rough creative idea into a complete, production-ready AI drama or motion comic plan.

It doesn't generate videos — it **generates the blueprint**: script, storyboard, reference image prompts, camera direction, sound design, continuity plan, and assembly guide. Everything you need to go straight to tooling like Seedance, 即梦, and 剪映.

### Two Modes, One Framework

| Mode | Best For | Output | Toolchain |
|---|---|---|---|
| **🎬 Film Mode** | Cinematic short films, trailers, AI video contests | Video prompt pack + storyboard + continuity plan | Seedance / 即梦 图生视频 |
| **🎞️ Motion Comic Mode** | Narrative-driven stories, voiceover-heavy content, rapid iteration | Panel mapping + batch prompts + 剪映 assembly guide | 即梦 出图 + 剪映 装配 |

> **Picking a mode:** Want cinematic camera movement and continuous video? → **Film mode.** Want a faster, voiceover-driven pipeline with consistent stills? → **Motion comic mode.** Default to film for spectacle, motion comic for story-driven efficiency.

---

## ✨ Why This Skill?

Most AI video projects fail *before* generation — not because the tooling is bad, but because the *plan* is weak.

**This skill solves four real problems:**

1. 🧠 **"I have an idea but don't know where to start"** — The intake → four foundations → production pipeline gives you a repeatable process, not a blank page.

2. 🎭 **"My characters look different in every shot"** — Reference image prompts lock character identity, costume, scene layout, and props *before* you generate a single video. Cross-reference checks ensure every `@图片` is actually used and every visual noun is covered.

3. 🎬 **"The shots don't cut together"** — Film continuity rules handle state tracking, cut type design, transition shots, dialogue breath gaps, and match-action cuts. AI clips are memoryless — this skill gives them memory.

4. 📝 **"My prompt engineering is inconsistent"** — Templates enforce narrative film direction (not keyword piles), time-coded beat density, inline dialogue/SFX/music, and automatic style prefix injection.

### Under the Hood

This workflow is distilled from real production experience: award-winning Jimeng shorts ("梦镜"), viral AI video postmortems, Seedance 2.0 multimodal pipelines, and multiple finished AI short dramas. Every principle in the skill is learned the hard way — so you don't have to.

---

## 👥 Who Is This For?

| Audience | Why It Matters |
|---|---|
| **AI video creators** | Move from "prompting in the dark" to systematic production planning |
| **Indie filmmakers** | Prototype scenes and sequences before committing to traditional production |
| **Content studios** | Standardize team workflows with repeatable, auditable production bibles |
| **Motion comic artists** | Get voiceover timing, panel mapping, and keyframe animation specs in one pass |
| **AI tool tinkerers** | Understand how Seedance, 即梦, and 剪映 fit together in a real pipeline |

No coding required. The output is pure Markdown — read it, follow it, generate from it.

---

## 🚀 Features at a Glance

### Shared (Both Modes)

- **🏗️ Four Foundations** — Worldbuilding, character bible, scene bible, style bible. Lock these first.
- **🖼️ Reference-First Design** — Every character, scene, and prop gets a dedicated reference image prompt before any video prompt is written.
- **✅ Cross-Reference Validation** — Automatic completeness check: every `@图片` in prompts exists in the material table, and every material entry is used by at least one prompt.
- **🔗 Reference Coverage** — Every visual noun in the action description that has a corresponding `@` entry *must* be cited in the prompt. No orphan references.
- **🧠 Mental Simulation Gate** — Before committing, dry-run the video in your head: story logic → scene continuity → physical plausibility → dialogue-action match.
- **🎨 Cover/Thumbnail Design** — Dedicated cover prompts with title text placement, using the same character/scene references.

### Film Mode Exclusive

| Feature | What It Does |
|---|---|
| **Multi-Agent Script Development** | 3-5 rounds of adversarial discussion between screenwriter, director, audience rep, and compliance reviewer. Every round records problems, feedback, and revision decisions. |
| **导演讲戏 (Director Analysis)** | Beat-by-beat breakdown: *concrete actions*, camera movement, light, emotion, sound. Turns "this scene is sad" into "character A turns away, light hits her left eye at 3s, exhale at 4.5s". |
| **Storyboard Table** | Per-shot: duration, visual references, camera, action beats, dialogue/sound cues, generation prompt |
| **Continuity Plan** | State tracking across clips, cut type selection, shot-size angle rotation (≥30°), transition shots, dialogue breath gaps (0.5s buffer), match-action opportunities |
| **Seedance Multimodal Prompt Pack** | `@图片/@视频` references with explicit purpose labels, time-coded segments (0-3s / 3-7s / etc.) |
| **Inline Sound Embedding** | Every video prompt contains `[对白]`, `[音效]`, `[配乐]` markers embedded in the matching time segment. Sound is not an afterthought. |

### Motion Comic Mode Exclusive

| Feature | What It Does |
|---|---|
| **Voiceover Timing Breakdown** | 中文按 3-4 字/秒 auto-estimate. One line maps to 1-2 panels. |
| **Panel-to-Voiceover Mapping** | Every voiceover line → matching panel(s) with timing and transition buffer |
| **Batch Image Prompts** | Unified style prefix auto-injected, character reference auto-linked |
| **4 Camera Motions, By Function** | push-in (emphasis), pull-out (release/ending), pan (transition), zoom (detail/reveal) — assigned by emotional function, not variety |
| **Color Temperature Consistency** | Adjacent panels must not jump warm→cold without a transition panel |
| **剪映 Assembly Guide** | Per-panel duration, keyframe animation, multi-track audio, timeline layout |

---

## 📦 What You Get (Output Contract)

After running the skill, you receive a single comprehensive Markdown document containing **everything** needed to produce your project.

### Film Mode Output

```
📄 Production Bible
├── 📋 Project Brief & Creative Direction
├── 🌍 Worldbuilding, Theme & Story Structure
├── 📝 Multi-Agent Script (3+ rounds of adversarial development)
├── 👤 Character Bible (visual design + reference prompts)
├── 🏠 Scene/Location Bible (reference prompts)
├── 🎨 Style Bible (color, lighting, lens, rhythm, sound, forbidden drift)
├── 🎬 Director Analysis (beat-by-beat 讲戏)
├── 📊 Storyboard Table (per-shot: duration, refs, camera, action, dialogue)
├── 🔗 Continuity Plan (state tracking, cut types, transition shots, matching)
├── 🎥 Video Prompt Pack (time-coded, inline audio/SFX/music)
├── 🖼️ Cover/Thumbnail Designs
└── ✅ Production Checklist (assets → rough cut → audio → iteration → compliance)
```

### Motion Comic Output

```
📄 Production Bible
├── 📋 Project Brief & Creative Direction
├── 🌍 Worldbuilding, Theme & Scene Outline
├── 👤 Character Bible + Scene Bible + Style Bible
├── 🎙️ Voiceover Script (per-line timing)
├── 📊 Panel-to-Voiceover Mapping Table
├── 🖼️ Batch 即梦 Image Prompts (style prefix + character refs)
├── 🎥 Camera Motion Assignment (push/pull/pan/zoom per panel)
├── ✂️ 剪映 Assembly Guide (timeline, durations, keyframes, tracks)
├── 🔊 Sound Plan (TTS/recording, ambience, effects, music)
└── ✅ Review Gates (7+ scoring checkpoints)
```

---

## ⚡ Quick Start

```bash
# 1. Install the skill
git clone https://github.com/Amouren7/ai-drama-production.git \
  ~/.claude/skills/ai-drama-production

# 2. In Claude Code, invoke with your idea
/ai-drama-production 我想做一个赛博朋克题材的AI短片
```

**What you'll need ready:**
- A story premise (even 2-3 sentences works)
- Optional: reference images (character designs, scene references)
- Target platform and approximate length

The skill walks you through the rest — mode selection, creative direction, and full production planning.

---

## 🔄 Real-World Workflow

### Film Mode
```
💡 Intake → 🏗️ Four Foundations (World → Character → Story → Style)
              → 🎬 Director Analysis (讲戏)
              → 📊 Storyboard + Seedance Prompt Generation
              → 🖼️ Still-Image Rough Cut → 🔄 Iteration
              → 🔊 Sound Pass → ✅ Review → 📦 Final Export
```

### Motion Comic Mode
```
💡 Intake → 🏗️ Four Foundations (shared)
              → 🎙️ Voiceover Script + Timing
              → 📊 Panel Mapping
              → 🖼️ Batch Image Prompt Generation
              → 🎥 Camera Motion Assignment
              → ✂️ 剪映 Assembly Guide
              → 🔊 Sound Plan → ✅ Review → 📦 Export
```

---

## 📂 Project Structure

```
ai-drama-production/
├── SKILL.md                          # Skill manifest, entry point, core rules
├── agents/
│   └── openai.yaml                   # Agent configuration
├── references/
│   ├── workflow.md                   # Film mode full workflow
│   ├── workflow-motion-comic.md      # Motion comic full workflow
│   ├── templates.md                  # Film mode templates
│   ├── templates-motion-comic.md     # Motion comic templates
│   ├── production-practice.md        # Tactical lessons from finished productions
│   └── review-checklists.md          # 7+ scoring gates with PASS/WARN/FAIL
├── README.md                       # Default: Chinese
├── README.en.md                    # English (this file)
└── LICENSE
```

---

## 🔧 Toolchain Requirements

| Tool | Film Mode | Motion Comic Mode |
|---|---|---|
| **Image/Video Gen** | Seedance 2.0 or 即梦 | 即梦 (or compatible image gen) |
| **Editing** | 剪映, Premiere Pro, or any NLE | 剪映 (keyframe, multi-track audio) |
| **Voiceover** | Human recording or TTS | 剪映 TTS, third-party TTS, or recording |
| **Claude Code** | ✅ Required for skill execution | ✅ Required for skill execution |

> **Standalone note:** The output Markdown is fully standalone — once generated, you can follow it without Claude Code. Just prompts, assembly guides, and workflow instructions.

---

## 🧠 Design Principles

| Principle | Why It Matters |
|---|---|
| **Story first** | Premise, conflict, and emotion drive audience retention — not tool trivia |
| **Consistency by design** | Lock references *before* generating prompts, not after |
| **Rough cut before final** | Still-image rough cuts catch timing/composition problems cheaply |
| **Sound is storytelling** | Voiceover, ambience, effects, and music each serve a distinct narrative function |
| **Output is production-ready** | Every document is a complete guide from assets to assembly |
| **Audit the joints** | Adjacent-shot continuity and cut quality determine perceived quality more than any individual shot |

---

## 🤝 Contributing

This skill is a living document — the workflows, templates, and rules grow as the AI video tooling landscape evolves.

- **Found a gap?** Open an issue or PR
- **Have a production postmortem?** Add it to `references/production-practice.md`
- **Disagree with a rule?** Propose the change with your reasoning — every rule here came from a real failure

---

## 📄 License

MIT — use it, fork it, build on it.

---

## 🔗 Related

- [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) — How skills work
- [Seedance](https://seedance.com) — AI video generation platform
- [即梦](https://jimeng.jianying.com) — AI image/video generation (by 剪映)
- [Claude Code](https://claude.ai/code) — AI coding assistant

---

<p align="center">
  Made with ❤️ for the AI filmmaking and motion comic community
</p>
