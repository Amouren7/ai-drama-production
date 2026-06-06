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
5. Keep prompts narrative and concrete.
6. Write only changes not already shown by references.

Use one generation prompt for one coherent generation unit. For complex action, generate multiple variations and plan edit points.

### 5.5 Storyboard Panel Generation (NEW — Before Any Video Generation)

**为什么先做分镜板图：**

文字提示词描述的构图在经过视频模型时会被"重新想象"一次。用生图AI先生成静态分镜板图，相当于在视频生成之前加一道视觉把关：构图是否准确、角色位置是否合理、光影方向是否一致、景别切换是否流畅。一张图改构图只需一次生成；一段视频改构图就要重做整个镜头。

**5.5.1 从视频提示词生成分镜板图**

为每个镜头生成一张静态分镜板图：

- 提取视频提示词中 `0-1秒` 的关键帧描述作为生图提示词主体
- 保持与视频提示词相同的画幅比例（9:16 / 16:9）
- 引用同一套角色参考图（@图片1 阿杰、@图片2 阿May 等）
- 引用场景参考图（@图片5 街道场景等）
- 移除视频提示词中的时间分段、运镜、声音等非图像信息
- 保留：角色位置、表情、服装、构图、景别、光影方向

> 一条视频提示词 → 一张分镜板图。不需要为每帧生图，只生"开场关键帧"即可。

完整提示词模板见 `references/templates.md` → "Storyboard Panel Prompt Template"。

**5.5.2 分镜板图审查清单**

生成所有镜头的分镜板图后，按以下要点逐一检查：

| 检查项 | 说明 |
|--------|------|
| 角色一致性 | 角色面容、服装、身材是否和角色参考图一致 |
| 构图准确性 | 是否和文字分镜描述一致（人物位置、背景元素） |
| 景别切换 | 相邻镜头的景别是否有明显变化（避免连续三个中景） |
| 光影方向 | 主光源方向是否跨镜头一致（除非有明确的光源变化理由） |
| 角色视线 | 对话场景中人物视线方向是否正确匹配（正反打规则） |
| 情绪表达 | 角色的表情是否传达了该镜头需要的情绪 |
| 场景衔接 | 前后镜头的空间位置关系是否逻辑连贯 |
| 穿帮检查 | 有没有出现不应该在这个场景出现的道具/角色/文字 |

完整审查清单模板见 `references/templates.md` → "Storyboard Panel Review Checklist"。

**5.5.3 审查决策**

每张分镜板图的审查结果：

- **✅ 通过** — 直接进入下一阶段
- **🔄 修改提示词后重新生成** — 构图或角色不满足要求，修改生图提示词后重试
- **📝 保留但标注风险** — 构图可用但有细微问题，在视频生成时通过 @图片 参考+提示词修正来弥补
- **❌ 废弃并重写分镜** — 文字分镜本身在视觉上不可行，退回 Step 5 修改文字分镜

不通过的镜头不应进入视频生成阶段。

**5.5.4 分镜板图 → 视频提示词注入**

审查通过的分镜板图作为该镜头的视觉参考，注入到 Seedance 视频提示词中：

- 在视频提示词的引用素材表中，将该镜头的分镜板图添加为 `@图片` 参考
- 在提示词正文中声明："以 @图片N（本镜头分镜板图）的构图和角色位置为基础"
- 提示词正文中不再重复描述已由图展示的静态信息（角色长相、服装颜色、场景布局），只描述图中没有的：动作、运镜、时间变化、声音

**改造前（无分镜板图参考）：**

```prompt
以 @图片1 中的阿杰为主角。生成 4 秒，9:16 竖屏。
0-1秒：阿杰站在路边，身穿黑色皮夹克，墨镜，午后阳光...
```

**改造后（分镜板图作为 @图片 参考）：**

```prompt
以 @图片1 中的阿杰为主角，以 @图片5（本镜头分镜板图）的构图和角色位置为视觉基准。生成 4 秒，9:16 竖屏。
0-1秒：阿杰从静止状态开始——他清了清嗓子，头转向右侧，嘴唇微动准备说话。场景光影和角色位置与参考图保持一致。
1-4秒：他手臂指向画外方向，然后转身走向机车，跨腿——皮裤卡在车把上，身体歪了一下。
```

注意看：改造后不再描述"站在路边""身穿黑色皮夹克""午后阳光"（已在图中），只描述"开始动"的部分。

## 6. Iteration And Assembly

Use a loop:

1. Generate a short MVP scene.
2. Score story hook, identity consistency, action clarity, camera feasibility, audio, and compliance.
3. Keep usable portions; mark flaws.
4. Rewrite only the failing segment.
5. Scale from one scene to full episode only after style and references are stable.

For action scenes, expect editing. Generate multiple takes, use match cuts, keep the best 60-80%, and replace broken motion with alternate angles or reaction shots.

## 7. Practical Production And Post

Create a still-image rough cut before generating final video. Use the approved storyboard panels from Step 5.5 as the primary rough-cut material:

1. Place storyboard panels (from Step 5.5) on a timeline at their assigned shot durations.
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
