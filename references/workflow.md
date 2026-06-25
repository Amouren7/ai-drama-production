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

### Film Mode Low-Input Defaults

Film mode is designed for low manual workload. Ask at most five essentials, then fill the rest:

- genre/tone
- protagonist and relationship seed
- first-episode hook
- ending question or cliffhanger
- target platform

Default to 60-90s, vertical 9:16, Chinese dialogue, short-drama pacing, 8-14 main shots plus bridge/insert insurance shots. The user should only need to review story direction, choose reference images or takes, and approve repairs. Anime-style still images with simple motion also use this film-mode workflow with gentler camera moves and simpler action beats.

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

## 2.5 Multi-Agent Script Development

Before locking the script, run a structured discussion loop. This applies even to 15-25s shorts.

Required roles:

- **Screenwriter A:** proposes the strongest premise, character desire, escalation, and ending button.
- **Screenwriter B or script doctor:** attacks weak logic, predictable beats, soft jokes, long dialogue, and missing reversals.
- **Director:** checks whether each beat can be shown as visible action, with clear blocking, camera, sound, and edit points.
- **Audience representative:** checks whether the first 3 seconds hook, the core conflict, and final payoff are understandable without explanation.

Run at least 3 rounds and at most 5 rounds:

1. **Round 1 — independent premise drafts.** At least two roles propose or compare story routes.
2. **Round 2 — cross-critique and integration.** Each route gets at least 3 specific improvement notes, then combine the strongest elements.
3. **Round 3 — final challenge and approval.** Agents challenge remaining issues, then approve a final script or the producer makes a documented decision.
4. **Optional rounds 4-5 — repair only.** Use only when logic, pacing, compliance, or generation feasibility still fails.

Each round must record:

- previous-round problems
- agent feedback
- concrete revision decisions
- unresolved issues
- next-round target

The final script package must include the iteration log before the polished script. Do not present a script as final if the three-round discussion is missing.

### Style

Define a style bible:

- art direction: medium, era, palette, texture, realism level
- camera grammar: handheld, locked-off, dolly, tracking, close-ups, one-take, montage
- lighting: source, direction, color temperature, contrast
- sound: dialogue density, ambience, music tempo, sound effects
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

Generate character references in stages for every main character:

1. **Clean turnaround lock:** one simple sheet on a white or light neutral background. It should include full-body front, side, and back views, plus optional half-body front/side/back views when face and costume need extra clarity. The goal is not atmosphere; the goal is stable identity, body proportion, hairstyle, costume, shoes, silhouette, and signature props.
2. **Full character design board:** one richer concept sheet after the clean turnaround is accepted. It may include a large hero portrait, orthographic turnaround, expression strip, costume/detail panels, work/daily/story-state looks, accessories, color palette, style keywords, and mood stills.

The clean turnaround is the identity anchor for later stills and video prompts. The full board is the creative bible for expressions, variants, props, and story context.

For major AI drama characters, create a **visual development sheet** before final prompts:

- story role: dramatic function, desire, wound, contradiction, arc
- commercial visual positioning: genre tier, realism/stylization level, beauty/texture direction
- identity profile: age, gender, region/nationality if relevant, height, body type, one-line identity
- face: facial structure, eyes, brows, nose, lips, expression set, skin tone, skin texture
- hair: hairstyle, color, hair volume, strand/detail quality
- costume: style, layers, silhouette, top/bottom/shoes, material, color blocking, wear state
- body and posture: proportion, stance, body language, physical signature
- premium anchors: accessories, tattoos/scars, props, color cards, fabric/metal/leather/skin material notes

Use an **advanced character board** when consistency is high-stakes. The board should include:

- left hero portrait or face close-up with skin/hair/facial detail
- center orthographic front/side/back full-body turnaround with identical pose and lighting
- expression strip with 4-6 controlled emotions using the same face
- outfit/style looks when story needs variants, clearly labeled as work mode, daily look, disguise, injury state, or race/combat mode
- mood stills that show the character in reusable story environments
- local detail panels for eyes, hair, neckline, hands, waist, tattoos/scars, accessories, weapons, tools, or signature props
- small color-card blocks for the dominant palette and style keywords

Keep the board controlled: neutral/light background for turnaround panels, cinematic backgrounds only in mood-still panels, no unmarked costume or hairstyle drift, no extra characters, no logos/watermarks, and only necessary measurement labels. If a variant is included, state what remains locked and what changes.

For variants, mark clearly:

- New: first appearance
- Reuse: no design change
- Variant: same identity with new costume/injury/age/state

### Reference Image Extraction Pass

When the user provides a strong reference image but the prompt language is weak, extract it before writing production prompts:

1. **Line-art cleanup:** convert the image into clean black line art on a white background, repairing structure, patterns, ornaments, and missing details.
2. **Flat color extraction:** analyze the color construction and produce a flat color draft with clear palette relationships.
3. **Reverse-prompt analysis:** deconstruct the image into subject, composition, style, materials, palette, lighting, lens, and quality controls, then write a reusable prompt that can recreate the visual logic across tools.

Use this pass for visual consistency, character design, props, costumes, and scene style references. Do not let it override script logic, shot continuity, or safety/compliance rules.

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
- updated state data for rows after the first: character position, standing/sitting state, eyeline, face direction, gesture, emotion, prop state, and lighting continuity
- join strategy for rows after the first: cut type, shot-size/angle change, transition insert if needed, dialogue breath gap, and match-action opportunity

Avoid literary descriptions that cannot be drawn, such as "responds with affection" or "symbolizes fragile life." Rewrite as visible action.

Create a material map first:

| Reference | Purpose | Notes |
|---|---|---|
| @图片1 | protagonist identity | face/costume reference |
| @图片2 | main location | layout and atmosphere |
| @视频1 | camera/action reference | use motion rhythm only |

For each shot:

1. State references and purpose.
2. State duration and aspect ratio.
3. For every shot after the first, state updated state data inherited from the previous shot.
4. State the join strategy: intentional cut, new shot size/subject, camera angle change of about 30 degrees or more when applicable, transition insert, breath gap, or match-action cut.
5. Describe time-coded action if longer than 10 seconds.
6. Include camera movement, character action, emotion shift, dialogue, and sound cues.
7. **Embed sound inline without audio references**: every dialogue line, sound effect, ambience, and music cue goes directly in the prompt at the correct time position using `[对白]` `[音效]` `[配乐]` markers. Do not create or cite `@音频` entries.
8. Keep prompts narrative and concrete.
9. Write only changes not already shown by references.

Use one generation prompt for one coherent generation unit. For complex action, generate multiple variations and plan edit points.

## 5.1 Copy-Paste Prompt Packaging

In film mode, output prompts in task-labeled blocks so the user can paste them directly into image/video tools:

- `IMAGE_START`: still image for the first frame of a shot
- `IMAGE_END`: still image for the last frame of a shot
- `IMAGE_MID`: optional middle keyframe when a 5-10s action has a crucial state change
- `VIDEO_MAIN`: video prompt for the shot, focused on motion from start to end
- `VIDEO_BRIDGE`: video prompt whose only job is to cover a join
- `VIDEO_INSERT`: short cutaway prompt for hands, eyes, prop, door, light, phone, tool, feet, reaction, or environment
- `VIDEO_REPAIR`: fallback prompt when the generated clip breaks identity, action, or continuity

For image-to-video, the image anchors carry composition, subject, lighting, and style. The video prompt should focus on subject action, camera motion, environmental motion, timing, and direction. Do not bury the motion under repeated static description.

Each prompt block must include: references, duration, aspect ratio, task purpose, copy-paste prompt, expected usable cut range, known failure modes, and repair prompt.

## 5.5 Mentally Simulate Before Generating

**Critical step: Before sending any prompt to the video model, run a mental simulation of the final video.**

Do this:
1. Read each prompt aloud in sequence, imagining what the video output would look like.
2. **剧情逻辑检查**: Does each shot's action follow logically from the previous? If character A is sad about gas prices in shot 3, does their action in shot 4 (e.g., pulling out a wallet) make sense as a consequence?
3. **场景连贯检查**: Would the lighting, character positions, and props be consistent across adjacent shots? Is a character's clothing the same? Is a mug that was full in shot 1 still full in shot 2?
4. **动作-对白匹配检查**: When a character says "I'm charging my phone," are they actually holding a phone and a charger? Or are they doing something unrelated?
5. **时间可行性检查**: Can the described action actually happen within the specified duration? (e.g., "stands up, walks 5 meters, pulls out phone, opens app" in 2 seconds is too much)

If the simulation reveals a logic gap or inconsistency, **rewrite the prompt before generating**. Do not "fix it in post" — fix it in the prompt.

## 5.6 Segment Continuity — Director Thinking For AI Joins

AI clips are memoryless: the next generated clip has no reliable knowledge of the previous clip's final frame. Treat every join as a directed edit, not as a hidden technical splice.

For each join:

1. **Update data.** Record changed positions, posture, eyelines, face direction, emotion, prop state, costume state, and lighting direction.
2. **Avoid same-shot continuation.** Do not rely on a previous tail frame as the next clip's first frame when the goal is a seamless same-camera continuation.
3. **Cut with contrast.** Change shot size or subject: medium to insert, wide to close-up, person to prop, close-up to reaction.
4. **Change angle.** When cutting the same subject, rotate the camera about 30 degrees or more; 45 or 90 degrees is safer.
5. **Use transition inserts.** Use meaningful inserts such as hands, phones, doors, vehicle lights, mirrors, environmental details, or reactions to cover state changes.
6. **Leave breath gaps.** Put silence, reaction, breath, or physical setup at clip starts/ends so dialogue does not feel chopped.
7. **Match action.** Start a movement in one clip and finish it in another angle or on another subject.
8. **Keep raw clips clean.** Generate raw clips without burned-in subtitles or baked-in background music; add these in editing.

### Join Contract Gate

Before writing final video prompts, create a Join Contract for every adjacent shot pair.

| Field | Required decision |
|---|---|
| Previous end state | exact pose, screen side, eyeline, prop, lighting, emotion |
| Next start state | exact pose, screen side, eyeline, prop, lighting, emotion |
| State delta | what changes between the two shots |
| Risk level | low / medium / high / forbidden-hard-cut |
| Hard cut allowed? | yes only if the state delta is small or intentionally hidden |
| Bridge required? | yes for high-risk and forbidden-hard-cut joins |
| Bridge prompt id | concrete `VIDEO_BRIDGE` or `VIDEO_INSERT` id |
| First/last-frame fit | good / risky / do not use |
| Safety inserts | available cutaways if the join fails |
| Sound bridge | ambience, breath, foley, dialogue overlap, music hit |
| Fallback edit | what to cut to if generation fails |

Risk scoring:

- **Low:** same location, same posture, small gaze/hand/emotion change.
- **Medium:** same location with moderate posture or prop change; use a reaction or insert if the cut feels sharp.
- **High:** location change, large posture change, carry/rescue, two-body interaction, entry/exit, prop state change, or missing action causality. Generate a bridge.
- **Forbidden-hard-cut:** "suddenly elsewhere", lying-to-standing without action, carried-to-seated without placement, impact aftermath, transformation, vehicle travel, costume/body-state change. Split into multiple bridge shots.

First/last-frame rule: use it only when the start and end frames share similar subject, scene, lighting, and style, or when a longer 10s transition can plausibly bridge the difference. If location and lighting both change, create intermediate frames or bridge shots instead.

### Bridge Shot Auto-Generation

For every high-risk or forbidden-hard-cut join, generate at least one of these bridge types:

- **Action bridge:** completes missing physical causality, e.g. lifting, setting down, opening a door, plugging a cable.
- **Spatial bridge:** shows travel or crossing, e.g. exiting a factory, vehicle lights, entering a workshop.
- **Prop bridge:** cuts through an object state, e.g. phone screen, key turns, cable connects, tool sparks.
- **Reaction bridge:** hides continuity with face response, breath, shock, pain, decision.
- **Light/sound bridge:** flashlight wipe, door slam, power flicker, engine sound, alarm, glitch pulse.

Do not leave bridge shots as optional suggestions. Add them to the shot list with prompt ids and durations.

## 6. Iteration And Assembly

Follow the MVP-first principle. Do not generate all shots before reviewing:

1. **Select MVP scene.** Pick the most technically demanding 1-2 shots (e.g., the core reversal).
2. **Generate MVP shots first.** Create the MVP shots, review the output.
3. **Score** story hook, identity consistency, action clarity, camera feasibility, sound design, and compliance.
4. **Keep usable portions; mark flaws.** If the MVP fails, rewrite the failing prompt and regenerate.
5. **Scale to remaining shots.** Only after the MVP scene passes, generate the remaining shots.

For action scenes, expect editing. Generate multiple takes, use match cuts, keep the best 60-80%, and replace broken motion with alternate angles or reaction shots.

## 6.5 Sound Design — Inline in Prompts, Not Separate References

**Critical rule: Every video prompt must embed dialogue, sound effects, ambience, and music inline.** Do not create audio material references, do not cite `@音频`, and do not write audio information as separate notes, tables, or "audio columns" outside the prompt. Seedance/即梦 multimodal generation reads sound cues from the prompt text itself. Format:

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
5. Keep all sound instructions inside the shot prompt; the material map remains visual-only.

## 7. Practical Production And Post

Create a still-image rough cut before generating final videos — lay out existing reference images, supplemental keyframes, or placeholder panels in a timeline to review shot sequence and pacing:

1. Place available scene/character/prop references, generated keyframes, or simple placeholder panels on a timeline at their assigned shot durations.
2. Check shot-size variety, character screen direction, POV clarity, and dialogue rhythm.
3. Adjust missing reaction shots or inserts before spending video-generation budget.
4. Use voice timing to decide whether shots need to be longer, shorter, or supplemented.

In film mode, the still rough cut has two passes:

1. **Anchor pass:** generate or select start/end frames only; assemble them in order to catch broken geography, posture jumps, and missing bridge actions.
2. **Motion pass:** generate video only for approved anchors; after each batch, extract candidate cut points and review joins before generating the next batch.

Always create an edit insurance package before final assembly:

- reaction close-ups for main characters
- hand and prop inserts for every important object action
- environment plates for each location
- door/light/phone/tool/vehicle inserts for transitions
- short 1-2s silent breath gaps for dialogue joins
- alternate takes for high-risk body interaction shots

Use layered video generation when multiple subjects must move:

- separate foreground character, background, props, and secondary character when a single generation is unstable
- create green-screen or transparent-background character motions when possible
- composite in editing software, then add shadows, blur, camera movement, and sound to unify

Use first/last frame generation for controlled motion, falls, reveals, entrances, transformations, and camera-position changes. Expect multiple attempts; mark probability-sensitive shots in the plan.

Do frame interpolation and upscaling before final edit export when source clips are low frame rate. Do not export a low-FPS rough edit to 30 FPS and then interpolate; interpolate the original generated clips first.

Design sound in passes:

- scratch voice: set rhythm and approximate duration
- final performance: record or generate after picture timing is clear
- ambience/effects: footsteps, paper, doors, machine hum, glitch, flashback, impacts
- music: use only where it strengthens genre, suspense, reveal, or climax; avoid overfilling dialogue scenes
