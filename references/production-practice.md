# Production Practice Notes

Use this reference when the user wants a practical, finished-film workflow rather than only a writing or prompting document.

## Lessons From An Award-Winning Jimeng Short

The "梦镜" production breakdown adds these operational principles:

- Choose a safer, clearer premise early. The team changed "police investigates murders and discovers he is the murderer" into "detective investigates thefts and discovers he is the thief" to reduce gore, improve worldbuilding, and fit platform constraints.
- Decide the type/style before designing assets. "Pixar-style anthropomorphic animals" made character identity, tone, and safety easier to control.
- Main characters need three-view sheets because they become pad/reference images for later shots.
- Do not design every supporting character before storyboard. Delay secondary characters until the shots prove they are needed.
- Create one high-quality core location image for heavily reused scenes; it may carry a large percentage of the film.
- AI-generated storyboard tables need human review. They are useful for structure but often miss viewpoint, shot-size variation, facial expression, and adjacent-shot continuity.
- Convert literary beats into draw-able instructions: "who does what" or "what object is where".
- Rough-cut still images before generating video. The still timeline reveals bad shot size, awkward perspective, missing reaction shots, and dialogue timing problems cheaply.
- For dialogue scenes, vary medium shot, medium close-up, close-up, insert, over-the-shoulder, relationship shot, and subjective POV.
- For difficult multi-character motion, split assets into layers and composite rather than forcing one video model to solve everything.
- Do not underinvest in sound. Voice performance, ambience, effects, glitches, and music cues are part of storytelling, not polish at the end.

## Practical Tool Pattern

Do not prescribe one fixed tool stack. Instead choose by job:

| Need | Useful Pattern |
|---|---|
| Fast visual exploration | text-to-image draft, then iterate |
| High-quality character/style | image reference into stronger image model |
| Core character consistency | three-view character sheet |
| Complex scene composition | background + characters + props as layers |
| Bad hands/props/edges | inpainting/local redraw/Photoshop generative fill |
| Perspective impossible for AI | manual compositing and local repair |
| Text must not deform | still motion / 2.5D parallax / post-composited text |
| Controlled transition/fall/reveal | first-frame and last-frame generation |
| Multiple moving characters | green-screen/transparent layer generation plus compositing |
| Low FPS or soft clips | interpolate and upscale original clips before final edit |
| Music cue | generate many variants, cut usable segments, loop/duck/fade in edit |

## Storyboard Audit Questions

For every storyboard row, ask:

1. Can an artist draw this from the sentence alone?
2. Is the viewpoint explicit: first-person, third-person, over-the-shoulder, subjective POV?
3. Is the shot size explicit and varied from adjacent shots?
4. Is the character expression concrete enough to act?
5. Does this shot connect spatially to the previous shot?
6. Does this shot motivate the next shot?
7. Is there an insert, reaction shot, or close-up where emotion or information needs emphasis?
8. Is the instruction doing too much for one AI video generation?

## Still Rough-Cut Protocol

Before final video generation:

1. Put all still frames/storyboard images into an editing timeline.
2. Add scratch dialogue or temporary voice.
3. Adjust each still's duration to match speech and readable action.
4. Check shot-size rhythm: establishing -> relation -> close-up -> insert -> reaction.
5. Add missing reaction, insert, and transition frames.
6. Only then generate moving clips for shots that survive the still edit.

## Audio Pass Protocol

1. Create scratch voice from the current storyboard to lock approximate shot length.
2. Use the rough cut to brief voice actors or TTS: emotion, pace, pauses, and subtext.
3. Record or generate final voice after timing is stable.
4. Add ambience and foley for every quiet shot: footsteps, fabric, paper, doors, devices, room tone.
5. Use effects for subjective states and transitions: glitch, pulse, rewind, flashback, impact.
6. Add music selectively. For suspense/reveal, ask for mystery, progression, pulse, restraint, and climax; then cut the usable section rather than forcing the whole generated track.

## Motion Comic Production Lessons

These lessons come from producing realistic and sci-fi motion comics with 即梦 + 剪映.

### Voiceover-Driven Panel Timing

The biggest difference between film and motion comic is timing. Motion comic timing is entirely voiceover-driven. A single voiceover line determines the panel duration, and the panel should hold long enough for the viewer to absorb both the image and the narration. Key rule: **read your voiceover aloud while watching the panel. If you finish reading before the panel ends, the hold feels natural. If the panel cuts before you finish reading, it will feel rushed.**

One common mistake is making panels too short. Unlike video where motion fills attention, a static panel needs more time for the eye to explore. Add 0.5-1.0 seconds of "reading time" per panel beyond the voiceover duration.

### Character Consistency In Independent Generations

Unlike video where a model has "inertia" across frames, each motion comic panel is independently generated. This makes character consistency the single biggest technical risk.

The practical fix is a three-layer approach:

- **Layer 1 — Reference image**: Every panel prompt must cite the same character reference image. This is non-negotiable.
- **Layer 2 — Style prefix**: Every panel prompt must start with the exact same style prefix string. Do not rewrite it per panel.
- **Layer 3 — Description anchor**: Every panel prompt must include the same 2-3 character identity anchors (e.g., "亚洲男性，28岁，短发，左眉尾旧伤疤").

If a character still drifts after applying all three layers, regenerate with a different reference image (try a closer-matching base) rather than endlessly rewording the prompt.

### Style Consistency Across Panels

Style drift between panels is subtle but destructive. A viewer may not notice it consciously, but they will feel that the panels "don't belong together."

Prevention checklist for each batch of prompts:

- All prompts start with the same style prefix.
- All prompts use the same color temperature logic (all cool-tone or all warm-tone unless intentionally shifting).
- All prompts specify consistent lighting direction (e.g., "主光源从左上45度照射" — then every panel respects this).
- Scene reference images are cited consistently.

### Rough Cut Before Full Image Generation

This is the single highest-ROI step in motion comic production. Before generating all 30+ panel images:

1. Use placeholder images (scene references or simple sketches) in 剪映.
2. Lay them out at estimated durations.
3. Add scratch voiceover (即使是手机录一段都可以).
4. Watch the rough cut. Adjust pacing.

This catches 80% of timing and composition problems before you spend time and credits on final image generation. It costs almost nothing and saves hours of rework.

### 剪映 Keyframe Efficiency

剪映's keyframe animation for still images is the magic that makes motion comic not feel like a slideshow. Key efficiency tips:

- Apply the same animation to a group of panels rather than setting each one individually. If all panels in a scene use push-in, set up the animation once and reuse.
- Use "自定义动画" presets (剪映 has built-in push-in/pull-out/pan animations that are good enough for most panels).
- Keyframe speed curves matter more than the motion itself. Always enable ease-in/ease-out unless you want an abrupt stop.
- Do not animate every panel. Some panels — especially wide establishing shots and emotional close-ups — work better completely still.

### Sound In Motion Comic

Motion comic sound is simpler than film sound but more deliberate. The hierarchy:

1. **Voiceover (最重要的)**: Crystal clear, properly timed, appropriate emotion. Bad voiceover kills a motion comic faster than bad images.
2. **Ambience**: Every scene needs a background atmosphere layer. A completely silent panel feels dead, not dramatic.
3. **Key SFX**: One well-placed sound effect (a door closing, a breath, a machine powering up) is worth more than continuous background music.
4. **Music**: The last layer, not the first. Add music only where the emotion needs it. Many motion comics are more powerful with just voiceover + ambience.

### Batch Generation Strategy

Do not generate all panel images at once. Batch by scene:

- Generate all panels for Scene 1 first.
- Check consistency and style.
- If Scene 1 passes, proceed to Scene 2 with the same reference setup.
- If Scene 1 has drift, fix the style prefix/character references before continuing.

This prevents waste: if your approach has a fundamental consistency problem, you catch it after 5-8 panels instead of 40.
