---
name: ai-drama-production
description: "Guide users from zero to a complete AI drama, motion comic, or AI short series production plan. Use when the user wants to create an AI drama, AI short film, motion comic, Seedance/Jimeng video or image workflow, script-to-storyboard pipeline, character and scene reference prompts, shot prompts, production bible, or a final Markdown document covering plot, worldbuilding, characters, visual style, image prompts, scene breakdowns, video prompts, assembly guides, and review checklists."
---

# AI Drama Production

## Overview

Use this skill to turn a user's rough idea into a complete AI drama or motion comic production Markdown. Two production modes are available:

- **🎬 Film mode** — continuous video generation, shot-based, Seedance/即梦图生视频. Best for AI short films, trailers, and cinematic sequences.
- **🎞️ Motion comic mode** — panel-based still-image assembly, voiceover-driven, 即梦出图 + 剪映装配. Best for narrative-driven stories, sci-fi/realistic motion comics, and projects where asset consistency and iteration speed matter more than continuous motion.

Always produce a Markdown deliverable unless the user asks for another format.

## Quick Start

1. **Determine the production mode:**
   - Does the user want continuous video with cinematic camera movement? → **Film mode**
   - Does the user want a voiceover-driven narrative with high-quality still images and keyframe animation? → **Motion comic mode**
   - Unsure? Default to film mode for visual spectacle, motion comic mode for story-driven efficiency.

2. Ask only for missing essentials:
   - target length and format: trailer, 30-90s short, 3-minute episode, multi-episode series, motion comic
   - genre, tone, visual style, audience, platform
   - story seed: premise, protagonist, conflict, ending preference
   - constraints: tools, language, aspect ratio, available reference images, safety limits
3. If the user gives little detail, choose reasonable defaults and make them explicit.
4. Follow the appropriate workflow:
   - Film mode → `references/workflow.md`
   - Motion comic mode → `references/workflow-motion-comic.md`
5. Use the relevant templates:
   - Film mode → `references/templates.md`
   - Motion comic mode → `references/templates-motion-comic.md`
6. Run the review gates in `references/review-checklists.md` before finalizing.
7. After delivery, explicitly ask what feedback the user has; create a version 2 if needed.

## Output Contract

### Film Mode

The final Markdown must include:

- project brief and creative direction
- worldbuilding, theme, story structure, and episode/scene outline
- character bible with visual design and reference image prompts
- scene/location bible with reference image prompts
- style bible with color, lighting, lens, rhythm, sound, and forbidden drift
- director analysis: beat-by-beat "讲戏" using concrete actions, camera movement, light, emotion, and sound
- storyboard table with scene duration, references, camera, action beats, dialogue, audio, and generation prompt
- storyboard panel generation: per-shot static panel prompts, panel review checklist, panel-to-shot reference mapping
- Seedance-style multimodal prompt pack using clear `@图片/@视频/@音频` roles
- production checklist, asset workflow, rough-cut plan, audio plan, iteration plan, and quality/compliance review

### Motion Comic Mode

The final Markdown must include:

- project brief and creative direction
- worldbuilding, theme, story structure, and scene outline
- character bible with visual design and reference image prompts
- scene/location bible with reference image prompts
- style bible with color, lighting, cinematic texture, and forbidden drift
- voiceover script with per-line timing breakdown (中文按 3-4 字/秒估算)
- panel-to-voiceover mapping table: each voiceover line maps to one or more image panels
- batch 即梦 image prompts with automatic style prefix and character reference injection
- camera motion assignment: push-in / pull-out / pan / zoom assigned per panel
- 剪映 assembly guide with timeline layout, per-panel duration, keyframe motion, audio tracks
- sound plan: TTS or voice recording, ambience, effects, music, and per-scene emotion-to-music mapping

## Core Rules

- Treat story as the source of value. Spend more effort on premise, conflict, reversals, emotion, and audience retention than on tool trivia.
- Build visual consistency early. Create character and scene reference prompts before writing final video prompts.
- Treat the first confirmed core location as a reusable production anchor; design later shots around it when consistency matters.
- Write video prompts as narrative film direction, not keyword piles.
- Describe what changes in the shot. Do not repeat static details already visible in reference images.
- Make every storyboard row image-actionable: who/what, where, camera viewpoint, shot size, expression, and the relationship to the previous/next shot.
- Keep each continuous shot within beat density: about 1 action beat per 2.5 seconds. For 5 seconds, 1-2 beats is usually enough.
- For 10-15 second generations, use time ranges such as `0-3s`, `3-7s`, `7-12s`, `12-15s`.
- Reserve the first and last 0.5 seconds for setup and natural settling; avoid key action or dialogue there.
- Label every `@` reference by purpose, such as "以 @图片1 中的女主为主角" or "参考 @视频1 的运镜节奏".
- Respect platform limits when writing per-shot prompts: images up to 9, videos up to 3, audio up to 3, mixed input total up to 12, video reference/audio total durations up to 15s each, generation length 4-15s.
- Avoid negative wording in prompts. Replace "不要切镜" with "全程一镜到底", and "不要说话" with "角色保持沉默".
- Avoid real-person face reference material, copyrighted IP dependence, political sensitivity, sexualized minors, explicit sexual content, graphic violence, and unsafe imitation.
- Before video generation, rough-cut the still storyboard images to check shot size, perspective, dialogue timing, and scene continuity.
- Plan sound like performance: dialogue/voiceover sets timing, ambience and effects carry scenes without music, and music should mark genre, suspense, reveal, or climax.
- **Generate static storyboard panels before video generation.** After writing per-shot video prompts, generate one static panel image per shot using a text-to-image model before running any video generation. Review these panels for composition, character placement, lighting, shot size, and expression. Use the approved panels as `@图片` references in the final video prompts. This catches composition and continuity problems at the image cost, not the video cost.

### Motion Comic Core Rules

- Voiceover is the timing anchor. Every panel is driven by a voiceover line; panel duration equals voiceover line duration + 0.5s transition buffer.
- One script line maps to one or two panels. If a voiceover line exceeds 15 words (中文), split into two panels.
- All image prompts in a motion comic must share a unified style prefix. Build the prefix once from the style bible and prepend it to every panel prompt.
- Every character reference image must be referenced in every panel where that character appears. Do not rely on the model "remembering" the character.
- Limit 即梦 image prompt reference images to 3-4 per generation: 1 style reference + 1-2 character references + 1 scene reference.
- Use only 4 camera motions: push-in (进入内心/强调), pull-out (释放/远去/结束), pan (场景过渡/环境展示), zoom (强调细节/反转). Assign by the panel‘s emotional function, not by visual variety.
- Maintain color temperature consistency between adjacent panels. If panel N is warm indoor, panel N+1 should not jump to cold outdoor without a transition panel.
- If a character has costume or state changes across the story, generate a new character reference image for each variant state and label it clearly.
- Rough-cut still panels in 剪映 before generating all images: lay out placeholder images in timeline, check pacing with scratch voiceover, then replace with final generated images.
- Sound design for motion comic is simpler than film but more deliberate: voiceover TTS, scene ambience, key sound effects, and background music. Each serves a different track.

## Reference Loading

Load these only when needed:

### Film Mode

- `references/workflow.md`: full end-to-end film production process
- `references/templates.md`: intake questions, Markdown skeleton, character/scene/prompt templates
- `references/production-practice.md`: practical image/video/audio/editing tactics from finished AI short production

### Motion Comic Mode

- `references/workflow-motion-comic.md`: full end-to-end motion comic production process
- `references/templates-motion-comic.md`: panel mapping, batch prompt, motion assignment, and 剪映 assembly templates

### Both Modes

- `references/review-checklists.md`: scoring gates and repair strategies

## Source-Derived Principles

The workflow is distilled from six Feishu Wiki sources about AIGC video setting design, Seedance 2.0 multimodal usage, AI short drama production shifts, Agent + Skill storyboard systems, a viral AI video production postmortem, and the award-winning Jimeng short "梦镜" production breakdown. Preserve these learned principles:

- Start with four foundations: world, character, story, style.
- Convert scripts into visible physical actions before generating prompts.
- Use a producer/director/art-designer/storyboarder mental model even when one person does all work.
- Use reference images to lock identity, costume, scene layout, color, and atmosphere.
- Use short 10-15 second scenes as testable units, often with one reversal or audience-retention hook.
- Let generation results feed back into the next script iteration; do not force a fully frozen long script too early.
- Use AI for structure, but manually audit storyboard shot size, viewpoint, expression, and adjacent-shot continuity.
- Combine tools pragmatically: text-to-image drafts, high-quality image iteration, Photoshop/layering/inpainting, first/last frames, image upscaling, frame interpolation, still-image rough cuts, voice/audio passes, and final editing all matter.
