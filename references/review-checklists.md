# Review Checklists

Use PASS / WARN / FAIL. Any average score below 8/10 or any single item below 6/10 requires revision.

## Story And Script Review

Score 1-10:

- premise clarity: audience understands the core conflict quickly
- hook strength: first 3 seconds create curiosity or surprise
- character desire: protagonist wants something concrete
- conflict escalation: each scene increases pressure or reveals new information
- reversal density: every 10-15 seconds has a turn, reveal, joke, escalation, or emotional beat
- dialogue force: lines are short, playable, and character-specific
- emotional logic: actions follow motivation
- ending button: final image or line lands cleanly

Repair:

- If premise is vague, rewrite as "A [person] must [goal] before [deadline], but [obstacle]."
- If scenes feel flat, add a choice, secret, countdown, contradiction, or status reversal.
- If dialogue is long, cut to the most charged sentence.

## Multi-Agent Script Iteration Review

Score 1-10:

- role coverage: at least two distinct agent viewpoints participated, including story/script and director/visual feasibility
- round count: at least 3 discussion rounds were completed before final script approval, with no more than 5 rounds
- critique specificity: each critique names concrete story, logic, pacing, joke, emotion, visual, or audience-comprehension issues
- revision traceability: each round records previous problems, feedback, decisions, unresolved issues, and next target
- audience lens: at least one pass checks first-3-second hook, comprehension without explanation, retention, and payoff clarity
- director lens: at least one pass converts abstract beats into visible action, camera, blocking, sound, and edit feasibility
- disagreement resolution: final decisions explain why one route was selected or why a concern was overridden
- final script impact: the final draft is materially stronger than the first route, not just reformatted

Repair:

- If fewer than 3 rounds exist, run another discussion round before finalizing.
- If all agents agree too easily, force a script doctor or audience representative to attack weak logic, unclear stakes, soft jokes, and overlong dialogue.
- If feedback is vague, rewrite it as actionable notes tied to a beat, line, action, shot, or audience reaction.
- If the final script ignores unresolved issues, document a producer decision or revise the script.

## Director Analysis Review

Score 1-10:

- visible action: abstract emotion is translated into physical behavior
- action chain: movement flows continuously
- camera direction: lens distance and motion are clear
- lighting specificity: source, direction, color temperature, and contrast are concrete
- audio specificity: dialogue, ambience, effects, and music are controlled
- beat density: duration can support the number of actions
- story fidelity: every script beat is preserved or intentionally adapted

Repair:

- Replace "sad/angry/nervous" with posture, gesture, eye movement, breath, hand action, blocking.
- Replace "cinematic lighting" with exact source and direction.
- Split overloaded shots or extend duration.

## Art Design Review

Score 1-10:

- identity distinctiveness: face, silhouette, costume, and prop are memorable
- consistency anchors: stable traits are named
- style unity: all characters and scenes share one art direction
- generation clarity: image prompts avoid ambiguity
- scene usability: layouts are usable as reference images
- variant control: reuse/new/variant states are clear
- core location anchor: heavily reused scenes have a stable hero reference
- production repair plan: difficult hands, props, text, perspective, and multi-character compositions have a repair method

Repair:

- Add a signature prop, color block, hairstyle, or silhouette if a character is generic.
- Remove conflicting style words.
- For scene grids, remove characters unless needed for scale.
- For hard multi-character shots, split background, character, prop, and expression assets into layers before video generation.

## Storyboard Imageability Review

Score 1-10:

- viewpoint clarity: first-person/third-person/over-the-shoulder/subjective POV is explicit
- shot-size rhythm: adjacent shots vary intentionally
- expression clarity: facial expression and psychology are concrete
- adjacent-shot continuity: each shot connects spatially and emotionally to the previous/next shot
- imageability: each row can be drawn from the instruction
- simplicity: each shot is reduced to a clear "who does what" or "what object is where"

Repair:

- Replace literary meaning with visible action.
- Add reaction shots, insert shots, and close-ups where emotion or information is unclear.
- Rough-cut still images before final video generation when continuity is uncertain.

## Seedance Prompt Review

Score 1-10:

- reference roles: every `@` reference states its purpose
- Shot State Contract: every `VIDEO_MAIN` has reference roles, first visible frame, screen layout, subject/prop state, camera coverage mode, action transition, final visible frame, and hard limits
- first-frame clarity: the first frame can be drawn as a still image without guessing subject position, posture, eyeline, prop state, or environment
- static/dynamic separation: prompt describes changes, not repeated reference details
- narrative writing: reads like film direction rather than keyword tags
- duration fit: action beats match seconds
- camera feasibility: no contradictory camera moves; one coverage mode is chosen unless a planned cut sequence is explicitly supported
- per-beat camera language: each time range states camera position/movement/focus together with the visible action
- camera summary consistency: the final camera-language line only summarizes the per-beat camera path and does not introduce new angles, cuts, or motion
- final-frame clarity: the segment stops on a concrete edit point and does not leak into the next plot event
- audio design: at least ambience, dialogue, music, or sound effects are specified
- continuity: prior and next shots can connect
- platform limits: per-shot references stay within allowed counts
- single-prompt usability: normal segments can be generated from one paste-ready prompt without a required extra keyframe pass
- optional keyframe restraint: keyframe-controlled workflows are used only for difficult repairs or explicit user requests

Repair:

- If `@图片1 @图片2` is naked, rewrite as "以 @图片1 中的角色为主角，场景参考 @图片2 的空间布局".
- If the first frame is vague, add a Shot State Contract before rewriting the prompt body.
- If a 5s prompt has 4+ actions, cut to 1-2 actions or make it 10-15s.
- If a prompt asks for rapid hand/face/object alternation inside one continuous shot, split those into `VIDEO_INSERT` prompts or rewrite as a planned cut sequence.
- If camera language appears only at the end, move the relevant camera position/movement into each time range.
- If the final camera-language line adds a new angle, cut, or movement, add it to the right time beat or remove it.
- If the final frame advances into the next story event, stop earlier and define the intended cliffhanger or edit point.
- Replace negatives with positive instructions.
- For 10s+ prompts, add time-coded segments.

## Film Segment Continuity Review

Score 1-10:

- memoryless handoff: every new clip restates changed character, prop, eyeline, and scene state
- updated state data: storyboard rows specify who is standing/sitting, screen position, face direction, gesture, emotion, prop state, and lighting continuity
- intentional cut design: joins are treated as cuts, not forced same-shot continuations from a tail frame
- shot-size contrast: adjacent shots avoid near-identical size and composition unless deliberately motivated
- camera angle change: same-subject joins rotate about 30 degrees or more when possible
- transition coverage: continuity gaps use inserts, props, reactions, environment details, or other story-relevant transition shots
- breath gaps: dialogue and sound leave usable pauses around clip boundaries
- match-action logic: partial actions can begin in one clip and finish in the next from another angle or subject
- raw clip cleanliness: generated clips avoid burned-in subtitles and baked-in background music
- editability: each join has a repair strategy if identity, pose, or action continuity drifts
- Join Contract completeness: every adjacent shot pair has previous end state, next start state, state delta, risk level, hard-cut permission, bridge requirement, safety inserts, sound bridge, and fallback edit
- high-risk transition handling: every location change, posture jump, carry/rescue, two-body interaction, prop state change, or missing causal action has a generated bridge or insert prompt
- copy-paste prompt readiness: every normal segment has one `VIDEO_MAIN` prompt ready to paste; risky joins have bridge/insert/repair prompts without the user inventing missing details
- state-camera preflight: every `VIDEO_MAIN` passes first-frame, time-beat, camera-mode, and final-frame checks before delivery

Repair:

- If two clips jump, first simplify the neighboring `VIDEO_MAIN` prompts or redesign the join as a cut to a new shot size, angle, subject, or transition insert.
- If character positions drift, create an updated state reference image or add a precise state update before the next prompt.
- If dialogue feels clipped, add 0.5-1s of silence, reaction, breath, or physical setup at the start/end of the neighboring clips.
- If a same-subject cut feels jumpy, rotate the camera at least 30 degrees or cut to a prop/reaction shot.
- If raw clips contain subtitles or music, regenerate without them when possible, or repair/remove them before final edit.
- If a Join Contract is missing, do not finalize. Add it before writing or delivering video prompts.
- If a Shot State Contract is missing from a `VIDEO_MAIN`, do not finalize. Add it before writing or delivering the prompt.
- If a high-risk join says "hard cut allowed", change it to a bridge shot, insert shot, match-action cut, or explicit time/space transition.
- If the user would need to think up a missing bridge prompt, the skill failed. Generate the bridge prompt directly.

## AI Clip Join Breakage Review

Use this gate after still rough cut and again after generated clips are assembled.

Score 1-10:

- spatial continuity: viewers understand how the character moved from location A to B
- posture continuity: lying/sitting/standing/carried states change on screen or are hidden by a motivated insert
- action causality: every physical result has a visible cause
- prop continuity: key objects preserve state, position, and ownership
- eyeline/screen direction: characters look and move in coherent directions
- bridge coverage: high-risk joins have bridge shots or cutaways already generated
- sound masking: ambience, foley, breath, music hits, or dialogue overlap smooth necessary cuts
- edit insurance: enough inserts/reactions/environment plates exist to repair failed AI motion
- final button: the last image supports the cliffhanger instead of leaking energy into a neutral insert

Repair:

- Location jump -> add spatial bridge: exit, vehicle/light, door, arrival, room tone change.
- Posture jump -> add action bridge: lift, catch, sit down, lay down, stand, plug, release.
- Prop jump -> add insert: hand, object close-up, screen, cable, tool, lock, switch.
- Emotion jump -> add reaction: breath, eye close-up, silent beat, face turn.
- Weak ending -> end on face/reveal/decision, not neutral environment unless the object is the cliffhanger.
- Unusable main clip -> keep the best 40-70%, replace broken middle with insert or regenerate a shorter bridge.

## Postproduction Review

Score 1-10:

- still rough cut: storyboard images were checked in timeline before expensive generation
- voice timing: dialogue duration matches shot duration
- sound coverage: quiet scenes include ambience or foley, not dead silence
- music restraint: music supports genre/reveal/climax without flattening drama
- repair workflow: low-FPS, soft, or unstable clips have interpolation/upscale/compositing plan
- edit flexibility: hard action scenes have alternate takes, inserts, and match-cut options

Repair:

- Add scratch voice and retime shots before final prompts.
- Interpolate/upscale original generated clips before final export.
- Add ambience/effects before adding more music.

## Compliance Review

Flag and repair:

- real-person face references: use fictional AI-generated character references instead
- copyrighted IP dependence: transform into original characters/worlds; keep only high-level genre inspiration
- political sensitivity or real public figures: remove or fictionalize
- minors in sexualized contexts: remove
- explicit sex or graphic gore: soften or cut
- dangerous imitation instructions: remove procedural detail
- defamation or impersonation: avoid real names and likenesses

## Final Markdown Review

Before delivering:

- no unfinished placeholders remain
- script package includes a multi-agent iteration log with at least 3 rounds before final script approval
- all reference numbers in prompts exist in the material map
- each prompt has duration, references, camera/action, emotion, and sound
- every character and scene has a visual anchor
- production plan includes image asset workflow, still rough cut, audio passes, iteration, and edit strategy
- film-mode plans include segment continuity strategy: updated state data, intentional cut points, shot-size/angle changes, transition shots, breath gaps, and match-action opportunities
- assumptions and defaults are clearly stated
