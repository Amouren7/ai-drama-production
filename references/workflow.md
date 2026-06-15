# AI Drama Production Workflow

## 1. Intake And Defaults

Ask for missing information in compact batches. If the user is uncertain, propose defaults:

- format: 60-90s proof-of-concept short, vertical 9:16, Chinese dialogue, 6-8 shots
- structure: cold open hook, escalation, reversal, emotional button, title/end card
- generation unit: each Seedance-style prompt is 5-15 seconds
- review style: iterate one short scene first before scaling

Minimum viable intake:

- story seed: "who wants what, why now, what blocks them"
- genre/tone: suspense, romance, comedy, fantasy, sci-fi, historical, workplace, etc.
- visual style: live-action cinematic, anime, clay, ink, cyberpunk, wuxia, retro, commercial, etc.
- target output: trailer, episode, storyboard prompt pack, or complete production bible

## 2. Set The Four Foundations

### World

Define the stage of the story:

- time, place, geography, rules, technology/magic/social structure
- everyday texture: food, clothes, architecture, weather, language, tools
- pressure system: scarcity, taboo, hierarchy, law, danger, secret

Output as a compact world bible plus 5-10 visual keywords.

### Character

For each important character:

- basic profile: name, age range, role, occupation/status
- desire and wound: external goal, internal need, fear, contradiction
- visual hook: silhouette, face shape, hair, costume, prop, color, gesture
- arc: start state, midpoint shift, final change
- consistency anchor: 3-5 details that must never drift
- expression set: neutral, joy, anger, fear, shock, suspicion, sadness, triumph

Make main characters visually distinctive; AI video consistency improves when silhouettes, costumes, and props are unmistakable.
For anthropomorphic or stylized projects, choose the species/body type as part of characterization. The animal/object metaphor should express personality and story function, not just cuteness.

### Story

Convert the premise into a structure:

- one-sentence logline
- theme in one sentence
- conflict ladder: small obstacle -> larger reversal -> decisive choice
- scene outline: each scene must advance plot, reveal character, or escalate stakes
- retention plan: first 3 seconds hook; every 10-15 seconds adds a new question, reveal, or reversal

For longer work, start with a 30-60 second MVP scene to validate style and audience pull.

### Style

Define a style bible:

- art direction: medium, era, palette, texture, realism level
- camera grammar: handheld, locked-off, dolly, tracking, close-ups, one-take, montage
- lighting: source, direction, color temperature, contrast
- audio: dialogue density, ambience, music tempo, sound effects
- forbidden drift: what must not appear or change

## 3. Director Analysis: Turn Text Into Visible Action

Do not merely summarize the script. "讲戏" like a director:

- replace abstract emotion with visible behavior
- use continuous action chains
- specify camera direction and lens distance
- specify light source, direction, color temperature, and intensity
- include dialogue, silence, breath, ambient sound, and music cues
- preserve the dramatic intention of each beat

Example transformation:

- Weak: "She feels lonely when she gets home."
- Strong: "She pushes the door open. The entryway sensor light fails to turn on. Only a cold strip of streetlight cuts through the living-room curtain. She sits without removing her coat, staring at the unwashed cup on the coffee table. The camera slowly pushes from her profile to the cup; half her face is pale blue, half disappears into shadow."

## 4. Art Design: Lock Visual References

Create prompts for reference images before final video prompts.

### Character Reference Prompt

Generate one image per main character:

- left side: close-up face portrait
- right side: full-body front, side, and back turnaround
- plain background
- consistent style, costume, palette, and signature prop

For variants, mark clearly:

- New: first appearance
- Reuse: no design change
- Variant: same identity with new costume/injury/age/state

### Scene Reference Prompt

For locations, use grid images:

- up to 9 scenes: 3x3 grid
- 10-12 scenes: 3x4 grid
- 13-16 scenes: 4x4 grid

Each cell should have a distinct location label, no characters unless needed, consistent style and lighting logic.

For the most-used location, create a single hero reference image rather than relying only on a grid. Mark it as the core scene anchor and reuse it heavily to keep the film visually coherent.

### Practical Image Asset Pipeline

Choose tactics by problem:

- No clear visual idea: use a text-to-image draft model to create rough compositions, then use the best draft as image reference for a stronger style model.
- Character consistency: generate three-view sheets first, then use them as pad/reference images for final character art.
- Complex multi-character composition: generate background and characters separately, composite in an image editor, then use inpainting or local redraw to repair hands, props, edges, and perspective.
- Text-heavy signs/screens: avoid asking video models to preserve tiny text. Use still image motion or 2.5D parallax tools when text must stay legible.
- Image-to-video quality loss: upscale/repair important stills before animating them.

## 5. Storyboard And Video Prompting

Before video prompts, audit the storyboard as image instructions.

Each storyboard row must answer:

- viewpoint: first-person, third-person, over-the-shoulder, subjective POV, objective camera
- shot size: establishing shot, wide, medium, medium close-up, close-up, insert, detail
- subject/action: "who does what" or "what object is where"
- expression/psychology: concrete face or body state
- adjacent-shot relation: why this shot follows the previous one and how it leads to the next one

Avoid literary descriptions that cannot be drawn, such as "responds with affection" or "symbolizes fragile life." Rewrite as visible action.

Create a material map first:

| Reference | Purpose | Notes |
|---|---|---|
| @图片1 | protagonist identity | face/costume reference |
| @图片2 | main location | layout and atmosphere |
| @视频1 | camera/action reference | use motion rhythm only |
| @音频1 | music/sound reference | use tempo/emotion |

For each shot:

1. State references and purpose.
2. State duration and aspect ratio.
3. Describe time-coded action if longer than 10 seconds.
4. Include camera movement, character action, emotion shift, dialogue, and audio.
5. **Embed audio inline**: every dialogue line, sound effect, ambience, and music cue goes directly in the prompt at the correct time position using `[对白]` `[音效]` `[配乐]` markers.
6. Keep prompts narrative and concrete.
7. Write only changes not already shown by references.

Use one generation prompt for one coherent generation unit. For complex action, generate multiple variations and plan edit points.

## 5.5 Mentally Simulate Before Generating

**Critical step: Before sending any prompt to the video model, run a mental simulation of the final video.**

Do this:
1. Read each prompt aloud in sequence, imagining what the video output would look like.
2. **剧情逻辑检查**: Does each shot's action follow logically from the previous? If character A is sad about gas prices in shot 3, does their action in shot 4 (e.g., pulling out a wallet) make sense as a consequence?
3. **场景连贯检查**: Would the lighting, character positions, and props be consistent across adjacent shots? Is a character's clothing the same? Is a mug that was full in shot 1 still full in shot 2?
4. **动作-对白匹配检查**: When a character says "I'm charging my phone," are they actually holding a phone and a charger? Or are they doing something unrelated?
5. **时间可行性检查**: Can the described action actually happen within the specified duration? (e.g., "stands up, walks 5 meters, pulls out phone, opens app" in 2 seconds is too much)

If the simulation reveals a logic gap or inconsistency, **rewrite the prompt before generating**. Do not "fix it in post" — fix it in the prompt.

## 6. Iteration And Assembly

Follow the MVP-first principle. Do not generate all shots before reviewing:

1. **Select MVP scene.** Pick the most technically demanding 1-2 shots (e.g., the core reversal).
2. **Generate MVP shots first.** Create the MVP shots, review the output.
3. **Score** story hook, identity consistency, action clarity, camera feasibility, audio, and compliance.
4. **Keep usable portions; mark flaws.** If the MVP fails, rewrite the failing prompt and regenerate.
5. **Scale to remaining shots.** Only after the MVP scene passes, generate the remaining shots.

For action scenes, expect editing. Generate multiple takes, use match cuts, keep the best 60-80%, and replace broken motion with alternate angles or reaction shots.

## 5.6 Audio Design — Inline in Prompts, Not Separate Notes

**Critical rule: Every video prompt must embed its audio inline.** Do not write audio information as separate notes, tables, or "audio columns" outside the prompt. Seedance/即梦 multimodal generation reads audio cues from the prompt text itself. Format:

```prompt
0-3秒：[动作描述]
     [对白：角色说的台词]
     [音效：环境音/效果音描述]
3-7秒：[动作发展]
     [配乐：音乐描述]
```

For each shot, before writing the prompt:
1. Decide the dialogue line and its approximate spoken duration.
2. Decide the key sound effects and where they hit.
3. Decide ambient sound and music.
4. **Embed all of these inline** in the prompt at the correct time position.

Create an Audio Material Reference Table (à la 素材对应表) listing every `@音频` asset needed:

| 编号 | 类型 | 时长 | 用途 | 对应镜头 |
|:----:|:----:|:----:|------|:--------:|
| @音频1 | 环境音 | 5s | 停车场黄昏环境风声 | 全片 |
| @音频2 | 音效 | 1s | 群消息提示音×5 | 镜头01 |
| @音频3 | 对白 | 2s | 阿凯第一句台词 | 镜头01 |

## 7. Practical Production And Post

Create a still-image rough cut before generating final videos — lay out the scene compositions in a timeline to review shot sequence and pacing:

1. Place storyboard panels (generated in Step 5.5 first pass) on a timeline at their assigned shot durations.
2. Check shot-size variety, character screen direction, POV clarity, and dialogue rhythm.
3. Adjust missing reaction shots or inserts before spending video-generation budget.
4. Use voice timing to decide whether shots need to be longer, shorter, or supplemented.

Use layered video generation when multiple subjects must move:

- separate foreground character, background, props, and secondary character when a single generation is unstable
- create green-screen or transparent-background character motions when possible
- composite in editing software, then add shadows, blur, camera movement, and sound to unify

Use first/last frame generation for controlled motion, falls, reveals, entrances, transformations, and camera-position changes. Expect multiple attempts; mark probability-sensitive shots in the plan.

Do frame interpolation and upscaling before final edit export when source clips are low frame rate. Do not export a low-FPS rough edit to 30 FPS and then interpolate; interpolate the original generated clips first.

Design audio in passes:

- scratch voice: set rhythm and approximate duration
- final performance: record or generate after picture timing is clear
- ambience/effects: footsteps, paper, doors, machine hum, glitch, flashback, impacts
- music: use only where it strengthens genre, suspense, reveal, or climax; avoid overfilling dialogue scenes
