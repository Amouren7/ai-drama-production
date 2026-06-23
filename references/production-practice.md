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

## Still-Image And Anime Light-Motion Lessons

Use these when a project uses anime-style stills or lightly animated images instead of fully continuous live-action motion. This is still film mode: the same shot list, Join Contract, bridge-shot, and copy-paste prompt rules apply.

### Timing

Static or lightly animated images need more screen time than full-motion clips because the viewer needs time to read the composition. Add 0.5-1.0 seconds of reading time beyond the dialogue duration, especially for emotional close-ups or complex scene reveals.

### Consistency In Independent Images

Each still/keyframe is independently generated, so character consistency is a major risk. Use a three-layer approach:

- **Reference image:** cite the same character reference whenever the character appears.
- **Style prefix:** keep one style prefix for the whole project or scene batch.
- **Description anchor:** repeat 2-3 identity anchors such as age, hairstyle, scar, costume, or signature prop.

If identity still drifts, regenerate with a better reference image rather than endlessly rewording the prompt.

### Still Rough Cut Before Motion

Before generating video motion:

1. Put start/end frames or placeholder images in 剪映.
2. Lay them out with estimated durations.
3. Add scratch dialogue or voiceover.
4. Watch the rough cut and fix missing bridges, weak reactions, or confusing geography.

This catches most timing and composition problems before spending video-generation credits.

### 剪映 Keyframe Efficiency

Simple keyframe animation can be enough for anime stills and quiet scenes:

- Apply the same motion preset to a group of related shots.
- Use push-in, pull-out, pan, or zoom only when it supports the emotion or information.
- Enable ease-in/ease-out unless an abrupt stop is intentional.
- Do not animate every frame; some establishing shots and emotional close-ups work better nearly still.

### Batch Strategy

Generate by scene batch:

- Generate the first scene's keyframes first.
- Check identity, style, color temperature, and lighting direction.
- If the first batch passes, continue with the same references and style lock.
- If it drifts, fix references before scaling to the rest of the episode.
