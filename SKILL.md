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
- multi-agent script iteration log with at least 3 rounds of discussion before final script approval
- character bible with visual design and reference image prompts
- visual development bible for major characters: commercial positioning, face/hair/costume/body/material/color-card/local-detail anchors, and optional advanced character board prompts
- scene/location bible with reference image prompts
- style bible with color, lighting, lens, rhythm, sound, and forbidden drift
- director analysis: beat-by-beat "讲戏" using concrete actions, camera movement, light, emotion, and sound
- storyboard table with scene duration, visual references, camera, action beats, dialogue/sound cues, and generation prompt
- continuity plan for generated video segments, including updated state data, cut points, shot-size/angle changes, transition shots, dialogue breath gaps, and match-action opportunities
- scene-by-scene video prompts with dialogue/SFX/ambience/music inline in each prompt using `[对白]` `[音效]` `[配乐]` markers
- Seedance-style multimodal prompt pack using clear visual reference roles such as `@图片/@视频`; **do not create or cite `@音频` references in video prompts.** Dialogue, SFX, ambience, and music must be written only inside the matching time-coded prompt segments.
- cover/thumbnail design prompt for each video, with title text placement described in the composition
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
- **Mandatory multi-agent script development:** Before finalizing any script, run at least 3 rounds and at most 5 rounds of script discussion with at least two distinct agent viewpoints. Use roles such as screenwriter, director, audience representative, script doctor, prompt engineer, editor, or compliance reviewer. Do not skip this for short scripts.
- Each script discussion round must record: previous-round problems, agent feedback, concrete revision decisions, current unresolved issues, and the next-round target. The final script must state how the last round resolved or intentionally overrode disagreements.
- At minimum, one agent must challenge story logic and joke/emotional payoff, one agent must challenge visual/directorial feasibility, and one agent or role pass must represent the target audience's comprehension and retention.
- Build visual consistency early. Create character and scene reference prompts before writing final video prompts.
- For important AI drama or motion comic characters, separate **story role** from **visual development**. Story role covers desire, wound, arc, and scene function; visual development covers commercial positioning, face, hair, costume layers, body proportion, skin/material texture, accessories, color palette, and local detail panels.
- Use advanced character boards when identity consistency matters: include face close-up, front/side/back orthographic turnaround, full-body scale view, local detail panels such as hands/feet/hair/waist/tattoo/accessory, and a small color-card area. Keep pose, costume, hairstyle, lighting, and proportions consistent across all panels.
- Treat the first confirmed core location as a reusable production anchor; design later shots around it when consistency matters.
- Write video prompts as narrative film direction, not keyword piles.
- Describe what changes in the shot. Do not repeat static details already visible in reference images.
- Make every storyboard row image-actionable: who/what, where, camera viewpoint, shot size, expression, and the relationship to the previous/next shot.
- Keep each continuous shot within beat density: about 1 action beat per 2.5 seconds. For 5 seconds, 1-2 beats is usually enough.
- For 10-15 second generations, use time ranges such as `0-3s`, `3-7s`, `7-12s`, `12-15s`.
- Reserve the first and last 0.5 seconds for setup and natural settling; avoid key action or dialogue there.
- Label every `@` reference by purpose, such as "以 @图片1 中的女主为主角" or "参考 @视频1 的运镜节奏".
- **Complete reference coverage: every item in the 场景与道具设定 table must have a corresponding reference image prompt.** If a prop or scene is important enough to list, it needs a `@图片` entry in the 素材对应表 with a dedicated reference prompt. Without a reference image, the AI model cannot consistently render that prop across shots.
- **Every video prompt must cite ALL relevant visual references.** The prompt header must explicitly reference the character `@图片`(s) appearing in the shot, the scene `@图片`, the key prop `@图片`(s), and any visual/motion `@视频` reference. A prompt that says "阿强翻钱包" without citing `@图片6(钱包)` will not generate a consistent wallet. Rule: every visual noun in the action description that has a corresponding `@` entry must be cited.
- **Cross-reference completeness check before delivery:** verify that every `@图片` / `@视频` referenced in any video prompt actually exists in the 素材对应表, and vice versa — every visual entry in the 素材对应表 is actually used by at least one prompt.
- Respect platform limits when writing per-shot prompts: visual references must stay within model limits; do not use `@音频` references in this workflow, and keep dialogue/SFX/music as inline text cues inside the prompt.
- Avoid negative wording in prompts. Replace "不要切镜" with "全程一镜到底", and "不要说话" with "角色保持沉默".
- Avoid real-person face reference material, copyrighted IP dependence, political sensitivity, sexualized minors, explicit sexual content, graphic violence, and unsafe imitation.
- Before video generation, rough-cut the still storyboard images to check shot size, perspective, dialogue timing, and scene continuity.
- Plan sound like performance: dialogue/voiceover sets timing, ambience and effects carry scenes without music, and music should mark genre, suspense, reveal, or climax.
- **Embed dialogue/SFX/ambience/music inline in every video prompt.** Sound is not a separate material reference, column, or afterthought — every video prompt must contain its dialogue lines, sound effects, ambient audio, and music cues embedded directly in the matching time-coded prompt segments. Use `[对白：台词内容]` for dialogue, `[音效：描述]` for sound effects and ambience, and `[配乐：描述]` for music. Do not add `@音频` entries to the 素材对应表 and do not cite audio references in prompt headers.
- **Dialogue timing drives shot duration, not the other way around.** Before writing any video prompt, map each line of dialogue to its approximate spoken duration. If a line is ~2 seconds long, the shot containing it must be at least 2.5 seconds (including 0.5s buffer). Split long lines across multiple shots or shorten the line.
- **Mentally simulate the generated video before generating.** Before committing to final prompts, do a "dry run" in your head: play the video from start to end, shot by shot. Verify: (1) 剧情逻辑是否通顺 — does each action follow from the previous one? (2) 场景连贯性 — does the location, lighting, character position, and prop state stay consistent from shot to shot? (3) 动作合理性 — can the character physically do what the prompt describes in the given time? (4) 对白与动作的匹配 — does the dialogue match what's happening on screen? If any step feels off during simulation, fix the script or prompt before generating.
- **Design a cover/thumbnail for each video.** The cover is a static image that captures the most iconic or funny moment of the short, with space for the title text. Write a dedicated cover prompt that: (1) uses the same character/scene reference images to maintain visual consistency, (2) composes the frame to leave room for title text overlay (top or bottom), (3) captures the emotional peak or comedic hook of the video. Specify in the prompt where text should be placed, e.g. "上方预留标题文字空间". The title itself is added in post-production, not generated as part of the AI image.

### Film Segment Continuity Rules

Use these whenever a film-mode story needs multiple generated clips, or when a shot follows another shot closely in time.

- Treat AI video clips as memoryless. The next clip does not know the previous clip's final state unless you restate it through prompt text and reference images.
- Track two data layers:
  - **Stable data:** character reference sheets, core scene references, style bible, recurring props.
  - **Updated state data:** who is standing/sitting, screen position, face direction, eyeline, gesture, emotion, prop location/state, lighting direction, costume state, and what action just finished.
- Before each new clip, write a one-line **state update** if anything changed: "After shot 02, A is standing on frame left, facing B; B looks up from the table; the cup is now empty."
- Do not try to hide joins by making clip B continue clip A as the same camera shot from the same tail frame. AI regenerates reference images, so tiny differences become visible jumps. Prefer designing an intentional cut.
- At joins, cut to a different shot size or subject. Avoid adjacent shot sizes such as medium-to-medium-close if the subject and angle are nearly the same. Safer cuts include wide-to-close-up, medium-to-insert, close-up-to-reaction, person-to-prop, and action-to-environment.
- When cutting between two shots of the same subject, rotate the camera angle by at least about 30 degrees; 45 or 90 degrees is safer when the space allows it.
- Use purposeful transition shots to cover continuity gaps: prop inserts, phone screens, hands, door handles, vehicle lights, mirrors, reaction shots, environment details, pets, smoke, leaves, water, or other story-relevant elements.
- Leave dialogue breath gaps around joins. The last 0.5s of a clip and the first 0.5s of the next clip should usually allow silence, reaction, breath, or physical setup unless the cut is intentionally abrupt.
- Use match-action cuts: let clip A start a motion and clip B finish it from another angle or on another subject. Examples: hand reaches for key -> key close-up turns; rider raises visor -> reaction close-up; foot steps down -> wheel/ground insert.
- Do not generate burned-in subtitles or baked-in background music in raw video clips. Add subtitles, music, and final mix in editing so joins remain repairable.
- For every storyboard row after the first, include a **join strategy**: cut type, state update, whether a transition shot is needed, and how dialogue/sound bridges the cut.

### Motion Comic Core Rules

- Voiceover is the timing anchor. Every panel is driven by a voiceover line; panel duration equals voiceover line duration + 0.5s transition buffer.
- One script line maps to one or two panels. If a voiceover line exceeds 15 words (中文), split into two panels.
- All image prompts in a motion comic must share a unified style prefix. Build the prefix once from the style bible and prepend it to every panel prompt.
- Every character reference image must be referenced in every panel where that character appears. Do not rely on the model "remembering" the character.
- Limit 即梦 image prompt reference images to 3-4 per generation: 1 style reference + 1-2 character references + 1 scene reference.
- Use only 4 camera motions: push-in (进入内心/强调), pull-out (释放/远去/结束), pan (场景过渡/环境展示), zoom (强调细节/反转). Assign by the panel's emotional function, not by visual variety.
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
- For supplied reference images, use a visual extraction pass when helpful: line-art cleanup to clarify structure, flat color extraction to lock palette, then reverse-prompt analysis to capture reusable visual logic. Use this for style/character consistency, not as a substitute for story development.
- Combine tools pragmatically: text-to-image drafts, high-quality image iteration, Photoshop/layering/inpainting, first/last frames, image upscaling, frame interpolation, still-image rough cuts, voice/audio passes, and final editing all matter.
