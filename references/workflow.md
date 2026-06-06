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

### 5.5 Storyboard Panel Generation — One Prompt, Two Passes

**核心原则：同一条提示词，先用做出图，后以图为参考做视频。**

写好的视频提示词不需要另写一套"生图版"。同一段文字跑两遍：
1. **第一遍 -> 生图模型**：去掉时间轴分段和运镜描述，只保留开场关键帧 -> 出静态分镜板图
2. **审查通过后**：在图生视频模型中，将这张图作为 @图片 参考注入 -> 同一条提示词出视频

这样做的价值：生图模型擅长精确构图但不懂运动，视频模型擅长运动但构图全靠猜。先用生图锁定构图、角色位置、光影，再用视频模型"让画面动起来"——两个模型各司其职。

**5.5.1 第一遍：从视频提示词生分镜板图**

不需要另写提示词。直接用写好的视频提示词，做两处裁剪：

1. **移除** 时间分段（0-3秒、3-7秒）——生图模型不需要时间轴
2. **移除** 运镜描述（"镜头快速后拉""推近至特写"）和声音——静态图不需要运动
3. **保留** 角色位置、表情、服装、构图、景别、光影方向
4. **添加** （如果需要）"生成 1 张静态图像"，并在角色参考后追加场景/道具参考图

转换示例：

**原始视频提示词：**
```prompt
以 @图片1 中的阿杰为主角。生成 4 秒，9:16 竖屏，写实电影风格。

0-1秒：一个手机直播界面的特写画面，弹幕从底部向上滚动...
1-3秒：镜头快速向后拉出，露出一个25岁中国男性站在市郊街道上...
3-4秒：他清了清嗓子，嘴唇微动准备说话...

全程一镜到底，手持摄影轻微自然晃动...
```

**生图版（同一段文字，只裁剪不重写）：**
```prompt
以 @图片1 中的阿杰为主角，场景参考 @图片5 的街道布局和光照。生成 1 张静态图像，9:16 竖屏，写实电影风格。

一个25岁中国男性站在市郊街道上，身穿黑色机车皮夹克、墨镜，一手举着手机自拍杆，另一只手刚从后脑勺放下来，表情略带心虚，午后阳光从左上角照射，柏油路面和路边树影在背景中。嘴唇微张，头转向右侧。
```

> **规则**：提取 0-1秒 或开场秒的关键帧描述作为生图主体。不需要为每帧生图——一张开场关键帧就足够作为视频的构图参考。

**5.5.2 审查**

生成所有镜头的分镜板图后，逐张检查：

- **角色一致性**：角色面容、服装是否和角色参考图一致
- **构图准确性**：构图是否符合文字分镜意图
- **景别切换**：相邻镜头的景别是否错开（避免连续三个中景）
- **光影方向**：主光源方向是否跨镜头一致
- **角色视线**：对话场景中视线方向是否正确匹配
- **情绪表达**：表情是否传达了该镜头需要的情绪
- **穿帮检查**：有没有不该出现的内容

审查结果分三档：
- **✅ 通过** -> 进入下一阶段
- **🔄 重生成** -> 构图或角色不满足，修改生图提示词重试
- **❌ 废弃分镜** -> 文字分镜本身视觉上不可行，退回 Step 5 重写

完整审查清单模板见 references/templates.md -> "Storyboard Panel Review Checklist"。

**5.5.3 第二遍：分镜板图注入 -> 出视频**

审查通过的分镜板图作为该镜头的视觉参考，注入回**同一条**视频提示词：

1. 在提示词的引用素材中添加："镜头板图参考 @板图N"
2. 提示词正文中**不再重复**已在图中展示的静态信息（角色站在哪里、穿什么衣服、光影方向）
3. 提示词正文**只描述**图中没有的：动作、运镜、时间变化、声音

**注入前（第一次跑，做出图）：**
```prompt
以 @图片1 中的阿杰为主角。生成 1 张静态图像，9:16 竖屏。
阿杰站在路边，身穿黑色皮夹克，墨镜，午后阳光...
```

**注入后（第二次跑，用同一段文字做视频）：**
```prompt
以 @图片1 中的阿杰为主角，以 @板图2（镜头分镜板图）的构图和角色位置为视觉基准。生成 4 秒，9:16 竖屏。

0-1秒：阿杰从静止状态开始——他清了清嗓子，头转向右侧。
1-4秒：他手臂指向画外方向，转身走向机车，跨腿——皮裤卡在车把上。

全程自然手持感。
```

注意：注入后不再描述"站在路边""黑色皮夹克""午后阳光"（已在 @板图2 中），只描述"从静止开始动"的变化。

**MVP 节奏：不要一次性对所有镜头做第一遍（出图）。** 按照 Step 6 的 MVP 原则——先选 1-2 个关键镜头做完整的第一遍+第二遍，验证角色一致性、构图准确性和视频自然度，通过后再扩展到剩余镜头。这个循环是：

```
选 MVP 镜头 -> 第一遍出图 -> 审查 -> 第二遍出视频 -> 评分 -> 通过后扩展到全片
                                                          ↓ 不通过
                                                    调整提示词后重做
```

## 6. Iteration And Assembly

Follow the MVP-first principle. Do not generate all storyboard panels before any video — instead, complete both passes on one key scene first:

1. **Select MVP scene.** Pick the most technically demanding 1-2 shots (e.g., the core reversal).
2. **Complete both passes on MVP.** First pass (Step 5.5.1) to generate panels for the MVP scene only -> review -> second pass (Step 5.5.3) to generate video for the MVP scene only -> review video output.
3. **Score** story hook, identity consistency, action clarity, camera feasibility, audio, and compliance.
4. **Keep usable portions; mark flaws.** If the MVP fails, rewrite the failing segment and redo Step 5.5 for that shot.
5. **Scale to remaining shots.** Only after the MVP scene passes, generate storyboard panels for the remaining shots (first pass across all other shots), then generate their videos (second pass across all other shots).

For action scenes, expect editing. Generate multiple takes, use match cuts, keep the best 60-80%, and replace broken motion with alternate angles or reaction shots.

## 7. Practical Production And Post

Create a still-image rough cut before running the second (video) pass. Use the approved storyboard panels from Step 5.5 as the primary rough-cut material:

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
