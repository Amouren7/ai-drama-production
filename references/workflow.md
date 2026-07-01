# AI Drama Production Workflow

## 1. Intake And Defaults

Ask for missing information in compact batches. If the user is uncertain, propose defaults:

- format: 60-90s proof-of-concept short, vertical 9:16, Chinese dialogue, 6-8 shots
- structure: cold open hook, escalation, reversal, emotional button, title/end card
- generation unit: each Seedance-style prompt is 5-15 seconds
- review style: iterate one short scene first before scaling

### Choose Output Depth

Use the lightest output that still solves the user's request:

- **Quick prompt pack:** for prompt-only requests, small test scenes, character/scene reference packs, or short AI漫剧 segments. Keep the script debate compact and output only assumptions, production locks, references, storyboard rows, video prompts, risky joins, and review checks.
- **Full production bible:** for complete episodes, series planning, commercial handoff, or end-to-end production documents. Use the full workflow and all review gates.

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

Default to 60-90s, vertical 9:16, Chinese dialogue, short-drama pacing, and 8-14 main segments. The default production output is one complete video prompt per segment. Add bridge, insert, or repair prompts only for risky joins, failed clips, or explicitly requested precision. Anime-style still images with simple motion also use this film-mode workflow with gentler camera moves and simpler action beats.

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
- performance anchors: how this character typically shows emotion through face, hands, posture, breath, and voice

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

## 2.5 Script Development

Before locking a full production bible script, run a structured discussion loop. For quick prompt packs, compress this into a three-pass note that checks story logic, visual feasibility, and audience comprehension without expanding into a long transcript.

Required roles:

- **Screenwriter A:** proposes the strongest premise, character desire, escalation, and ending button.
- **Screenwriter B or script doctor:** attacks weak logic, predictable beats, soft jokes, long dialogue, and missing reversals.
- **Director:** checks whether each beat can be shown as visible action, with clear blocking, camera, sound, and edit points.
- **Audience representative:** checks whether the first 3 seconds hook, the core conflict, and final payoff are understandable without explanation.

For full production bibles, run at least 3 rounds and at most 5 rounds:

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

The final full production bible script package must include the iteration log before the polished script. Quick prompt packs should include a compact decision note instead of a long debate log.

### Style

Define a style bible, then compress it into reusable **production locks** for video prompts:

- art direction: medium, era, palette, texture, realism level
- camera grammar: handheld, locked-off, dolly, tracking, close-ups, one-take, montage
- lighting: source, direction, color temperature, contrast
- sound: dialogue density, ambience, music tempo, sound effects
- forbidden drift: what must not appear or change

Production locks are written once and inherited by every `VIDEO_MAIN`. Keep them compact and practical:

- **Character lock:** identity, costume, hairstyle, body proportion, signature prop.
- **Scene lock:** recurring location, spatial layout, lighting source, key set dressing.
- **Style core:** genre, era, realism/stylization level, emotional flavor.
- **Visual baseline:** lens/camera feel, shot texture, motion intensity, rendering target.
- **Color and lighting:** palette, contrast, light source, color temperature, atmosphere.
- **Motion rules:** how fast the camera and subjects may move; what movement is forbidden.
- **Continuity lock:** screen direction, prop states, posture/position data that must carry across joins.
- **Sound mood:** ambience, foley density, music behavior.
- **Forbidden drift:** style, identity, costume, location, subtitles, logos, or action types that must not appear.

Do not scatter unrelated style phrases into every shot. If a shot needs a variation, state it as a local exception to the production locks.

## 3. Director Analysis: Turn Text Into Visible Action

Do not merely summarize the script. "讲戏" like a director:

- replace abstract emotion with visible behavior
- for every important emotion, write the performance cause formula: **trigger -> facial details -> body action -> voice tone**
- use continuous action chains
- specify camera direction and lens distance
- specify light source, direction, color temperature, and intensity
- include dialogue, silence, breath, ambient sound, and music cues
- preserve the dramatic intention of each beat

Treat actors as responding to events, not displaying labels. "She is scared" is not ready for video generation; write what she sees or hears, then how her eyes, mouth, shoulders, hands, breath, and voice change. If the cause is missing, the AI often produces a fake pose toward the camera.

Example transformation:

- Weak: "She feels lonely when she gets home."
- Strong: "She pushes the door open. The entryway sensor light fails to turn on. Only a cold strip of streetlight cuts through the living-room curtain. She sits without removing her coat, staring at the unwashed cup on the coffee table. The camera slowly pushes from her profile to the cup; half her face is pale blue, half disappears into shadow."

Performance prompt pattern:

```text
真实情绪 = 发生原因 + 表情细节 + 肢体动作 + 说话语气
```

Example:

- Weak: "Lu Ye becomes terrified."
- Strong: "The brake lever suddenly goes loose while a truck enters the edge of the intersection. Lu Ye first frowns in disbelief, then his pupils widen and his jaw tightens; his right hand squeezes the brake again, shoulders locked, body lowering toward the motorcycle tank; he says '糟了' in a short, breathless voice."

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

Use this only as an advanced repair or migration path when the user provides a strong reference image but the prompt language is weak, ambiguous, or unstable:

1. **Line-art cleanup:** convert the image into clean black line art on a white background, repairing structure, patterns, ornaments, and missing details.
2. **Flat color extraction:** analyze the color construction and produce a flat color draft with clear palette relationships.
3. **Reverse-prompt analysis:** deconstruct the image into subject, composition, style, materials, palette, lighting, lens, and quality controls, then write a reusable prompt that can recreate the visual logic across tools.

Use this pass for visual consistency, character design, props, costumes, and scene style references. Do not make it part of the default workflow, and do not let it override script logic, shot continuity, or safety/compliance rules.

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

Before video prompts, audit the storyboard as a three-layer production document rather than a loose plot summary.

Each scene or shot group should separate:

1. **Fixed assets:** which character, expression, costume, location, prop, and recurring visual nodes are locked.
2. **Style and texture:** which parts of the production locks apply, plus local camera/lens/light/mood notes.
3. **Screen action:** what the audience sees happen, when it happens, how the camera moves, and where the edit can cut.

This structure prevents video prompts from becoming either vague story prose or overloaded keyword piles.

Each storyboard row must answer:

- viewpoint: first-person, third-person, over-the-shoulder, subjective POV, objective camera
- shot size: establishing shot, wide, medium, medium close-up, close-up, insert, detail
- subject/action: "who does what" or "what object is where"
- expression/psychology: concrete face or body state
- performance cause: what visible event triggers the emotion, then face/body/voice response
- adjacent-shot relation: why this shot follows the previous one and how it leads to the next one
- updated state data for rows after the first: character position, standing/sitting state, eyeline, face direction, gesture, emotion, prop state, and lighting continuity
- join strategy for rows after the first: cut type, shot-size/angle change, transition insert if needed, dialogue breath gap, and match-action opportunity

Avoid literary descriptions that cannot be drawn, such as "responds with affection" or "symbolizes fragile life." Rewrite as visible action.

### Shot State Contract

Before writing any `VIDEO_MAIN`, write a compact state contract. This is the guardrail against unclear initial states and broken camera logic.

Required fields:

| Field | Required answer |
|---|---|
| Reference roles | which reference locks identity, scene layout, prop design, expression, or motion rhythm |
| First visible frame | exact subject, posture, screen side, eyeline, prop position, and environment at second 0 |
| Screen layout | who/what is foreground, midground, background; left/right direction of motion |
| Subject state | body posture, hand state, face direction, emotion, and immediate intention |
| Performance Cause Contract | emotion trigger, facial details, body action, voice tone; required when the shot depends on acting |
| Prop/state data | location, ownership, visible condition, and what may change |
| Camera coverage mode | continuous single shot / single shot with focus shift / planned cut sequence / montage |
| Camera path | where the camera starts, how it moves, and where it ends |
| Action transition | the single state change this segment must accomplish |
| Final visible frame | final pose, prop state, eyeline, screen direction, and edit point |
| Hard limits | what the model must not advance into, plus the positive state it should stop on |

If the first visible frame cannot be drawn as a still image, the video prompt is not ready. If the final visible frame cannot connect to the next shot, revise the shot or add a bridge/insert.

Choose one camera coverage mode per generation by default:

- **Continuous single shot:** safest for action continuity; no hidden cuts.
- **Single shot with focus shift:** one shot that changes emphasis, such as hand -> face, without changing location or time.
- **Planned cut sequence:** only when the model/tool handles edit-like prompting; each cut must have a time range and a reason.
- **Montage:** only for compressed time, memories, screens, travel, or stylized summaries; do not use it for precise physical continuity.

When the prompt asks for multiple close-ups and medium shots inside one normal segment, first decide whether those are separate `VIDEO_INSERT` prompts, a planned cut sequence, or a simpler continuous shot. Do not let the model invent the edit.

Create a material map first:

| Reference | Purpose | Notes |
|---|---|---|
| @图片1 | protagonist identity | face/costume reference |
| @图片2 | main location | layout and atmosphere |
| @视频1 | camera/action reference | use motion rhythm only |

For each shot:

1. State references and purpose.
2. State duration and aspect ratio.
3. Write the Shot State Contract.
4. For every shot after the first, state updated state data inherited from the previous shot.
5. State the join strategy: intentional cut, new shot size/subject, camera angle change of about 30 degrees or more when applicable, transition insert, breath gap, or match-action cut.
6. Describe time-coded action if longer than 5 seconds or if the shot has more than one visible motion beat.
7. Put camera position and camera movement inside each time range together with character action, performance cause/reaction, dialogue, and sound cues.
8. **Embed sound inline without audio references**: every dialogue line, sound effect, ambience, and music cue goes directly in the prompt at the correct time position using `[对白]` `[音效]` `[配乐]` markers. Do not create or cite `@音频` entries.
9. Keep prompts narrative and concrete.
10. Write only changes not already shown by references.

Use one generation prompt for one coherent generation unit. For complex action, split the action into smaller prompts, generate multiple variations, and plan edit points.

### Time-Coded Video Prompt Discipline

Each `VIDEO_MAIN` should read like director instructions to the actor, camera, and sound team:

- **Inherited locks:** cite the production locks rather than rewriting the whole style bible.
- **Shot State Contract:** lock first frame, screen layout, camera mode, action transition, final frame, and hard limits before the prompt body.
- **Task:** one sentence saying the only job of this segment.
- **Start state:** where everyone and every key prop begins.
- **Time beats:** `0-1.5s`, `1.5-3s`, etc. Each beat describes a visible change.
- **Per-beat camera language:** every time beat states shot size/angle/movement/focus for that beat, following the camera coverage mode and path in the Shot State Contract.
- **Per-beat performance logic:** when emotion changes, the same time beat states the trigger, facial detail, body action, and voice tone. Do not let emotion appear without a cause.
- **Sound inline:** dialogue, foley, ambience, and music at the beat where they happen.
- **End state/edit point:** what final posture, prop state, or reaction the editor can cut on.
- **Do-not-drift list:** only the most important identity, costume, location, prop, and subtitle constraints.

Avoid writing a dense 10-second action scene as one prompt if it contains more than 4 physical actions, a location change, or more than two interacting bodies. Split it or add bridge/insert prompts.

Do not leave camera language only as a final summary. Use the final camera-language line only as an audit of the per-beat camera path. If the final line introduces a new angle, cut, or movement that does not appear in the time ranges, either add it to the correct time range or remove it.

Treat image references and prompt text differently: uploaded images should carry stable appearance, costume, face, prop design, and layout; prompt text should describe the dynamic change, camera path, audio, and final state. Repeating every static detail in every time beat increases drift and hides the real action.

## 5.1 Single-Prompt Copy-Paste Packaging

In film mode, keep the user's workload low: output one task-labeled `VIDEO_MAIN` block per segment as the default paste target. Do not require the user to generate start frames, end frames, and then video for every shot.

- `VIDEO_MAIN`: the complete video prompt for a normal segment. It includes references, duration, camera, action, state continuity, dialogue, sound effects, ambience, and music cues.
- `VIDEO_BRIDGE`: optional prompt whose only job is to cover a high-risk join.
- `VIDEO_INSERT`: optional short cutaway prompt for hands, eyes, prop, door, light, phone, tool, feet, reaction, or environment.
- `VIDEO_REPAIR`: optional fallback prompt when the generated clip breaks identity, action, or continuity.

Each `VIDEO_MAIN` prompt is a single coherent generation unit. It should be paste-ready, not a checklist that asks the user to assemble missing information. The prompt can mention the intended first beat and final beat in text, but it should not require separate image keyframe assets.

Each prompt block must include: references, duration, aspect ratio, task purpose, copy-paste prompt, expected usable cut range, known failure modes, and repair strategy.

Use optional keyframes only under these conditions:

- a specific motion repeatedly fails in single-prompt generation
- a keyframe-capable model is available and the user explicitly wants that workflow
- a controlled transformation, fall, reveal, or posture change cannot be solved with a shorter segment or bridge prompt

When optional keyframes are used, label them as `OPTIONAL_KEYFRAME` or `OPTIONAL_KEYFRAME_REPAIR` and keep them out of the default prompt list.

## 5.5 Mentally Simulate Before Generating

**Critical step: Before sending any prompt to the video model, run a mental simulation of the final video.**

Do this:
1. Read each prompt aloud in sequence, imagining what the video output would look like.
2. **首帧检查**: Can the first frame be drawn as a still? Are subject, posture, screen side, eyeline, prop position, and environment concrete?
3. **剧情逻辑检查**: Does each shot's action follow logically from the previous? If character A is sad about gas prices in shot 3, does their action in shot 4 (e.g., pulling out a wallet) make sense as a consequence?
4. **场景连贯检查**: Would the lighting, character positions, and props be consistent across adjacent shots? Is a character's clothing the same? Is a mug that was full in shot 1 still full in shot 2?
5. **镜头逻辑检查**: Does the camera coverage mode match the requested motion? A continuous shot cannot also demand rapid unrelated close-up alternation unless it is rewritten as a planned cut sequence.
6. **表演因果检查**: Does every important emotion have a visible trigger, facial details, body action, and voice tone? If someone suddenly looks afraid, what made them afraid on screen?
7. **动作-对白匹配检查**: When a character says "I'm charging my phone," are they actually holding a phone and a charger? Or are they doing something unrelated?
8. **时间可行性检查**: Can the described action actually happen within the specified duration? (e.g., "stands up, walks 5 meters, pulls out phone, opens app" in 2 seconds is too much)
9. **终帧检查**: Does the final frame stop at the intended cliffhanger/edit point without leaking into the next plot event?

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
| Bridge prompt id | concrete `VIDEO_BRIDGE` or `VIDEO_INSERT` id when needed |
| Optional keyframe fit | none / useful / repair-only |
| Safety inserts | available cutaways if the join fails |
| Sound bridge | ambience, breath, foley, dialogue overlap, music hit |
| Fallback edit | what to cut to if generation fails |

Risk scoring:

- **Low:** same location, same posture, small gaze/hand/emotion change.
- **Medium:** same location with moderate posture or prop change; use a reaction or insert if the cut feels sharp.
- **High:** location change, large posture change, carry/rescue, two-body interaction, entry/exit, prop state change, or missing action causality. Generate a bridge.
- **Forbidden-hard-cut:** "suddenly elsewhere", lying-to-standing without action, carried-to-seated without placement, impact aftermath, transformation, vehicle travel, costume/body-state change. Split into multiple bridge shots.

Optional keyframe rule: use first/last frames only as repair tooling, not as the default way to generate every segment. If location and lighting both change, prefer a new `VIDEO_MAIN` segment plus bridge or insert prompts.

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

In film mode, the default rough cut is lightweight: assemble the planned segment list, existing references, thumbnails, or placeholders to check story order, shot size, and dialogue timing. Do not require a full keyframe anchor pass unless the user asks for it or a difficult shot has already failed.

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

Use first/last frame generation only as an optional repair path for controlled motion, falls, reveals, entrances, transformations, and camera-position changes. Try a simpler `VIDEO_MAIN` prompt or a short bridge prompt first.

Do frame interpolation and upscaling before final edit export when source clips are low frame rate. Do not export a low-FPS rough edit to 30 FPS and then interpolate; interpolate the original generated clips first.

Design sound in passes:

- scratch voice: set rhythm and approximate duration
- final performance: record or generate after picture timing is clear
- ambience/effects: footsteps, paper, doors, machine hum, glitch, flashback, impacts
- music: use only where it strengthens genre, suspense, reveal, or climax; avoid overfilling dialogue scenes
