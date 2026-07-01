---
name: ai-drama-production
description: "Use when the user wants to plan or produce an AI drama, AI short film, AI漫剧, Seedance/Jimeng workflow, character or scene reference prompts, storyboard prompts, video prompt packs, continuity repair plans, or a production bible."
---

# AI Drama Production

## Overview

Use this skill to turn a user's rough idea into an AI drama production Markdown. Film mode is the default; choose the lightest output mode that satisfies the request.

- **🎬 Film mode** — the only production mode. It covers live-action AI shorts, cinematic sequences, anime-style image-to-video, simple still-image motion, trailers, and short episodes. The user provides the idea and reviews outputs; the skill produces one ready-to-copy video prompt per segment by default, plus optional bridge, insert, or repair prompts only when a cut is risky or a generated clip fails.

Always produce a Markdown deliverable unless the user asks for another format.

## Output Modes

- **Quick prompt pack:** use when the user asks for prompts, a short test scene, character/scene references, or a small AI漫剧 segment. Keep the script iteration compact, output only the sections needed, and still include style lock, reference coverage, time-coded `VIDEO_MAIN`, risky-join repair, and review checks.
- **Full production bible:** use when the user asks for a complete film/episode/series plan, production bible, commercial workflow, or end-to-end document. Include the complete output contract below.

## Quick Start

1. **Use film mode by default, then choose quick prompt pack or full production bible.**
   - Continuous AI video, anime-style image-to-video, simple still-image motion, and short-drama episodes all use the same film-mode workflow.
   - If the user wants anime images to move slightly, treat it as film mode with gentler camera motion and shorter action beats.
   - Copy-paste output is part of film mode, not a separate mode.

2. Ask only for missing essentials:
   - target length and format: trailer, 30-90s short, 3-minute episode, multi-episode series, anime image-to-video
   - genre, tone, visual style, audience, platform
   - story seed: premise, protagonist, conflict, ending preference
   - constraints: tools, language, aspect ratio, available reference images, safety limits
3. If the user gives little detail, choose reasonable defaults and make them explicit.
4. Follow `references/workflow.md`.
5. Use `references/templates.md`.
6. Run the review gates in `references/review-checklists.md` before finalizing.
7. After delivery, explicitly ask what feedback the user has; create a version 2 if needed.

## Output Contract

### Film Mode

For a full production bible, the final Markdown must include:

- project brief and creative direction
- worldbuilding, theme, story structure, and episode/scene outline
- multi-agent script iteration log with at least 3 compact rounds of discussion before final script approval
- character bible with visual design and reference image prompts
- visual development bible for major characters: commercial positioning, face/hair/costume/body/material/color-card/local-detail anchors, plus a staged character reference plan
- **character reference package for every lead character**: clean turnaround sheet first, then full character design board when identity consistency matters
- scene/location bible with reference image prompts
- **production locks** before shot prompts: character, scene, style, camera, continuity, sound mood, and forbidden drift
- director analysis: beat-by-beat "讲戏" using concrete actions, camera movement, light, performance cause, expression details, body action, voice tone, and sound
- storyboard table with a three-layer shot structure: fixed assets, style/texture inheritance, and time-coded screen action, plus a Shot State Contract for each generated segment
- continuity plan for generated video segments, including updated state data, cut points, shot-size/angle changes, transition shots, dialogue breath gaps, and match-action opportunities
- **Join Contract table for every adjacent shot pair**: previous end state, next start state, state delta, risk level, hard-cut permission, bridge-shot requirement, optional keyframe suitability, safety inserts, sound bridge, and fallback edit
- **copy-paste prompt pack**: one `VIDEO_MAIN` prompt per segment by default, each preceded by a Shot State Contract, with optional `VIDEO_BRIDGE`, `VIDEO_INSERT`, and `VIDEO_REPAIR` prompts for risky joins or failed generations
- scene-by-scene video prompts with dialogue/SFX/ambience/music inline in each prompt using `[对白]` `[音效]` `[配乐]` markers
- Seedance-style multimodal prompt pack using clear visual reference roles such as `@图片/@视频`; **do not create or cite `@音频` references in video prompts.** Dialogue, SFX, ambience, and music must be written only inside the matching time-coded prompt segments.
- cover/thumbnail design prompt for each video, with title text placement described in the composition
- production checklist, asset workflow, rough-cut plan, audio plan, iteration plan, and quality/compliance review
- low-input intake assumptions: genre, protagonist, first-episode hook, ending question, platform, aspect ratio, and defaults chosen by the skill
- risk-scored shot list with every transition classified as low, medium, high, or forbidden-hard-cut
- generated bridge or insert prompts for every high-risk or forbidden-hard-cut transition; do not leave repair work for the user to invent
- safety insert library: hands, eyes, props, doors, lights, phones, tools, feet, reaction faces, and environment plates that can cover broken joins
- copy-paste blocks labeled by generation task: `VIDEO_MAIN` for every normal segment, plus `VIDEO_BRIDGE`, `VIDEO_INSERT`, and `VIDEO_REPAIR` only where needed. Do not require separate image keyframe blocks in the default workflow.
- user review gates with simple choices: approve, regenerate, choose A/B/C, or request repair
- post-generation repair loop: after the user supplies clips, review cuts, identify broken joins, and output replacement bridge/insert prompts plus an edit decision list

For a quick prompt pack, include only the relevant subset: brief assumptions, production locks, required reference prompts, storyboard rows, `VIDEO_MAIN` prompts, risky `VIDEO_BRIDGE`/`VIDEO_INSERT`/`VIDEO_REPAIR` prompts, and review checks.

## Core Rules

- Treat story as the source of value. Spend more effort on premise, conflict, reversals, emotion, and audience retention than on tool trivia.
- **Script development:** Before finalizing a full production bible script, run at least 3 rounds and at most 5 rounds of script discussion with at least two distinct agent viewpoints. For quick prompt packs, compress this into a short three-pass note: story logic, visual/directorial feasibility, and audience comprehension.
- Each script discussion round must record: previous-round problems, agent feedback, concrete revision decisions, current unresolved issues, and the next-round target. The final script must state how the last round resolved or intentionally overrode disagreements.
- At minimum, one agent must challenge story logic and joke/emotional payoff, one agent must challenge visual/directorial feasibility, and one agent or role pass must represent the target audience's comprehension and retention.
- Build visual consistency early. Create character and scene reference prompts before writing final video prompts.
- For important AI drama characters, separate **story role** from **visual development**. Story role covers desire, wound, arc, and scene function; visual development covers commercial positioning, face, hair, costume layers, body proportion, skin/material texture, accessories, color palette, and local detail panels.
- For lead characters, use a **two-stage character reference workflow** when identity consistency matters:
  1. **Clean turnaround lock:** first generate a simple white/neutral-background sheet with front, side, and back full-body views, plus optional half-body face views. This locks face, body proportion, hair, costume, shoes, and silhouette before adding story atmosphere.
  2. **Full character design board:** after the clean sheet is acceptable, generate a richer board with hero portrait, orthographic turnaround, expressions, costume/detail panels, work/daily/story-state looks, mood stills, accessories, color palette, and style keywords.
- Do not treat a single beautiful portrait as a complete character reference. If the character will appear in multiple shots, the output must include reference prompts that reveal face, body, costume, and key props from multiple angles.
- Use advanced character boards when identity consistency matters: include face close-up, front/side/back orthographic turnaround, expression strip, outfit/style looks, mood stills, local detail panels such as eyes/hair/hands/waist/accessory/signature prop, and a small color-card area. Keep identity, core costume, hairstyle, lighting logic, and proportions consistent across all panels; variants must be labeled as variants rather than silently changing the base design.
- For generated character reference boards, prefer professional concept-art sheet composition over poster composition: clear panel hierarchy, neutral backgrounds for turnaround views, cinematic panels only for mood stills, and no crowded decorative typography.
- Treat the first confirmed core location as a reusable production anchor; design later shots around it when consistency matters.
- Write video prompts as narrative film direction, not keyword piles.
- Before writing any `VIDEO_MAIN`, write **production locks** once for the project or scene batch: character lock, scene lock, style lock, camera/motion lock, continuity lock, sound mood, and forbidden drift. Every shot prompt inherits these locks instead of restating random style words.
- Build each storyboard row in three layers before generating prompts:
  1. **Fixed assets:** characters, expressions, costumes, props, and locations that must stay locked.
  2. **Style and texture:** the inherited production locks plus any shot-specific lens, lighting, color, or movement flavor.
  3. **Screen action:** shot size, composition, camera movement, visible action, performance trigger, state change, dialogue/sound, and timing.
- Before every `VIDEO_MAIN`, write a **Shot State Contract**: reference roles, first visible frame, screen layout, subject state, prop state, camera coverage mode, action transition, final visible frame, and hard limits. If this contract is unclear, fix it before writing the prompt.
- When a character's emotion matters, add a **Performance Cause Contract** inside the Shot State Contract: `emotion trigger + facial details + body action + voice tone`. Do not write only abstract emotions such as "fearful", "angry", or "moved"; make the emotion arise from a visible event in the current or previous beat.
- For every `VIDEO_MAIN`, use time-coded action beats whenever the segment is longer than 5 seconds or contains more than one motion beat. Each time range must say what changes on screen, not repeat static descriptions.
- Put camera direction inside each time range, not only at the end. Each beat should say camera position/movement plus visible action plus performance reaction plus sound, while following the single camera path declared in the Shot State Contract.
- In time-coded beats, write performance as a causal chain: what the character sees/hears/realizes -> what changes in the face -> what the body does -> how the line is spoken. Example: "刹车把松空，他先皱眉不信，随后瞳孔放大、肩膀僵住，压低嗓子急促说：'糟了'。"
- State the first visible frame and final visible frame as camera-readable facts. Avoid vague starts such as "continues riding" or "danger approaches" unless the prompt also states position, posture, screen direction, visible props, and what changes first.
- Do not make video prompts dense action dumps. A normal 5-second prompt should contain 1-2 action beats; a 10-15 second prompt can contain several beats only if each beat is physically possible and has a clear edit point.
- Use one camera coverage mode per generation unless the user explicitly wants an edit-sequence prompt and the model supports it: **continuous single shot**, **single shot with focus shift**, **planned cut sequence**, or **montage**. Do not write "hand close-up, wheel close-up, medium shot rapid alternation" inside a normal continuous prompt; split into inserts or a planned edit sequence.
- The final "camera language" line should audit or summarize the per-beat camera path; it should not introduce new angles, cuts, or movements that were not already assigned to a time range.
- Describe what changes in the shot. Do not repeat static details already visible in reference images.
- Make every storyboard row image-actionable: who/what, where, camera viewpoint, shot size, expression, and the relationship to the previous/next shot.
- Every storyboard row must be generation-actionable: it needs one complete video prompt, expected failure modes, and a repair strategy. Do not ask the user to invent missing bridge shots.
- Keep each continuous shot within beat density: about 1 action beat per 2.5 seconds. For 5 seconds, 1-2 beats is usually enough; for 10-15 seconds, use ranges such as `0-3s`, `3-7s`, `7-12s`, `12-15s`.
- Reserve the first and last 0.5 seconds for setup and natural settling; avoid key action or dialogue there.
- Label every `@` reference by purpose, such as "以 @图片1 中的女主为主角", "参考 @图片2 的路口空间布局", or "参考 @视频1 的运镜节奏". Never leave naked references.
- **Complete reference coverage: every item in the 场景与道具设定 table must have a corresponding reference image prompt.** If a prop or scene is important enough to list, it needs a `@图片` entry in the 素材对应表 with a dedicated reference prompt. Without a reference image, the AI model cannot consistently render that prop across shots.
- **Every video prompt must cite the relevant visible references within platform limits.** The prompt header must explicitly reference visible character `@图片`(s), scene `@图片`, key prop `@图片`(s), and any visual/motion `@视频` reference used by that shot. If references exceed model limits, create a shot-specific reference bundle and prioritize visible characters, core costume, location, key props, and motion reference.
- **Cross-reference completeness check before delivery:** verify that every `@图片` / `@视频` referenced in any video prompt actually exists in the 素材对应表, and vice versa — every visual entry in the 素材对应表 is actually used by at least one prompt.
- Respect platform limits when writing per-shot prompts: visual references must stay within model limits; do not use `@音频` references in this workflow, and keep dialogue/SFX/music as inline text cues inside the prompt.
- Avoid negative wording in prompts. Replace "不要切镜" with "全程一镜到底", and "不要说话" with "角色保持沉默".
- When a prohibition is safety-critical, pair it with a positive target and a restrained exclusion list: "危险逼近但保持安全距离；画面停在未碰撞前" works better than only saying "不要撞车".
- Avoid real-person face reference material, copyrighted IP dependence, political sensitivity, sexualized minors, explicit sexual content, graphic violence, and unsafe imitation.
- Before video generation, do a lightweight rough cut using available references, thumbnails, storyboard stills, or placeholders to check shot size, perspective, dialogue timing, and scene continuity. Do not force a separate keyframe generation pass for every shot.
- Plan sound like performance: dialogue/voiceover sets timing, voice tone reveals emotion, ambience and effects carry scenes without music, and music should mark genre, suspense, reveal, or climax.
- **Embed dialogue/SFX/ambience/music inline in every video prompt.** Sound is not a separate material reference, column, or afterthought — every video prompt must contain its dialogue lines, sound effects, ambient audio, and music cues embedded directly in the matching time-coded prompt segments. Use `[对白：台词内容]` for dialogue, `[音效：描述]` for sound effects and ambience, and `[配乐：描述]` for music. Do not add `@音频` entries to the 素材对应表 and do not cite audio references in prompt headers.
- **Dialogue timing drives shot duration, not the other way around.** Before writing any video prompt, map each line of dialogue to its approximate spoken duration. If a line is ~2 seconds long, the shot containing it must be at least 2.5 seconds (including 0.5s buffer). Split long lines across multiple shots or shorten the line.
- **Mentally simulate the generated video before generating.** Before committing to final prompts, do a "dry run" in your head: play the video from start to end, shot by shot. Verify: (1) 剧情逻辑是否通顺 — does each action follow from the previous one? (2) 场景连贯性 — does the location, lighting, character position, and prop state stay consistent from shot to shot? (3) 动作合理性 — can the character physically do what the prompt describes in the given time? (4) 对白与动作的匹配 — does the dialogue match what's happening on screen? If any step feels off during simulation, fix the script or prompt before generating.
- **Run a performance-cause preflight before delivery.** For each important emotion, verify that the prompt states the trigger, face details, body action, and voice tone. If the emotion could appear without the triggering event, or if the face/body/voice contradict each other, rewrite the beat.
- **Run a state-camera preflight before delivery.** For each `VIDEO_MAIN`, check that the first frame can be drawn, every time beat follows from the previous beat, camera motion does not contradict the coverage mode, and the final frame can cut into the next Shot State Contract.
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
- For every adjacent shot pair, include a **Join Contract**. Required fields: `from shot`, `to shot`, `previous end state`, `next start state`, `state delta`, `risk level`, `hard cut allowed?`, `bridge shot required?`, `bridge prompt id`, `optional keyframe fit`, `safety inserts`, `sound bridge`, `fallback edit`.
- **Risk rule:** if location changes, character posture changes heavily (lying/sitting/standing/carried), a prop state changes, a character enters/exits, two bodies interact, or action causality is missing, mark the join high-risk. High-risk joins cannot be hard-cut without a generated bridge shot or insert.
- **Forbidden-hard-cut cases:** rescue/carry actions, combat impacts, falls, vehicle/location travel, transformation, costume/state change, and "suddenly arrives elsewhere." These must be split into bridge shots, insert shots, or simpler segment prompts.
- Keyframe-controlled generation is optional repair tooling only. Use it when a specific difficult motion cannot be solved by a single prompt or bridge prompt; do not make it the normal production path.
- Always generate an edit insurance package for film mode: at least 1 reaction shot per speaking character, 1 hand/prop insert for every key object action, 1 environment insert for every location, and 1 light/door/phone/tool insert for every scene transition.

## Reference Loading

Load these only when needed:

- `references/workflow.md`: full end-to-end film production process
- `references/templates.md`: intake questions, Markdown skeleton, character/scene/prompt templates
- `references/production-practice.md`: practical image/video/audio/editing tactics from finished AI short production
- `references/review-checklists.md`: scoring gates and repair strategies

## Source-Derived Principles

The workflow is distilled from six Feishu Wiki sources about AIGC video setting design, Seedance 2.0 multimodal usage, AI short drama production shifts, Agent + Skill storyboard systems, a viral AI video production postmortem, and the award-winning Jimeng short "梦镜" production breakdown. Preserve these learned principles:

- Start with four foundations: world, character, story, style.
- Convert scripts into visible physical actions before generating prompts.
- Convert emotional labels into playable performance: trigger, facial detail, body action, and voice tone.
- Use a producer/director/art-designer/storyboarder mental model even when one person does all work.
- Use reference images to lock identity, costume, scene layout, color, and atmosphere.
- Use text prompts primarily to describe subject/action, environment, camera, sound, and temporal change; let uploaded images carry static appearance details when references are strong.
- Use short 10-15 second scenes as testable units, often with one reversal or audience-retention hook.
- Let generation results feed back into the next script iteration; do not force a fully frozen long script too early.
- Use AI for structure, but manually audit storyboard shot size, viewpoint, expression, and adjacent-shot continuity.
- Use the visual extraction pass only as advanced repair or migration tooling when supplied references are ambiguous, unstable, or hard to reproduce: line-art cleanup, flat color extraction, then reverse-prompt analysis. Do not make it part of every default run.
- Combine tools pragmatically: text-to-image drafts, high-quality image iteration, Photoshop/layering/inpainting, optional first/last frames for difficult repairs, image upscaling, frame interpolation, still-image rough cuts, voice/audio passes, and final editing all matter.
