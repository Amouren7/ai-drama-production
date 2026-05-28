# Motion Comic Production Workflow

**Toolchain:** 即梦（图生图/文生图） + 剪映（动画+配音+剪辑）  
**Core principle:** Voiceover timing drives everything. Each voiceover line becomes one or two image panels. Panels are assembled in 剪映 with keyframe animation to simulate camera motion.

---

## 1. Intake And Mode Confirmation

Determine motion comic suitability:

- **Good fit:** narrative-driven stories, dialogue-heavy scenes, sci-fi/realistic settings with complex environments, projects where 100% visual consistency matters more than continuous motion
- **Poor fit:** action choreography with complex movement, music videos requiring precise lip-sync, projects needing natural physics and object interaction

If the user has existing materials, collect them early:
- script or story premise
- character reference images (if already generated)
- scene reference images (if already generated)
- reference voiceover or TTS samples (optional)

---

## 2. Creative Layer (Shared With Film Mode)

### 2.1 World

- time, place, geography, rules, technology
- everyday texture and atmosphere
- pressure system: what creates tension

### 2.2 Character

For each main character:

- basic profile: name, age, role, occupation
- desire and wound: external goal, internal conflict
- visual hook: silhouette, face shape, costume, prop, color
- consistency anchor: 3-5 visual details that must never drift across panels
- expression requirements for key scenes: neutral, fear, determination, grief, joy, etc.

### 2.3 Story

- one-sentence logline
- theme
- scene outline: each scene advances plot, reveals character, or escalates stakes
- for motion comic: note which scenes are heavy on voiceover (info-dump risk) and which are carried by visual atmosphere (no voiceover, pure emotion)

### 2.4 Style Bible

- art direction: medium, era, palette, texture, realism level
- cinematic texture: film grain, lens flare, depth of field, lighting quality
- for sci-fi: lighting source behavior (neon, hologram, cockpit glow, weapon charge), material properties (metal, glass, carbon fiber), HUD/interface style
- forbidden drift: what must not change across panels
- **Style prefix** — distill the style bible into one consistent prefix string. Every image prompt in the entire motion comic will use this prefix.

Style prefix example for a sci-fi project:

```text
写实电影风格，胶片颗粒感，高对比度，冷蓝主色调点缀琥珀色光，浅景深，暗部保留细节，科幻质感，自然光影，8K
```

---

## 3. Voiceover Script And Timing

This is the most important phase in motion comic production. The voiceover drives everything else.

### 3.1 Generate or accept the script

If the user provides a story seed, generate a complete voiceover script. If the user provides a script, use it directly.

### 3.2 Break the script into voiceover lines

Rules for line breaks:

- Each line should be a natural breath unit: one sentence or one clause.
- Aim for 8-15 words per line in Chinese. If a sentence exceeds 15 words, split it.
- Emotionally charged lines can be shorter (3-6 words) for emphasis.
- Lines longer than 20 words or exceeding 5 seconds are almost always too dense for one panel.

### 3.3 Estimate timing per line

中文语速估算标准：

- Normal narration: 3-4 字/秒
- Slow/emotional: 2-3 字/秒
- Fast/urgent: 4-5 字/秒

Calculate per line:

```text
line_text: "他站在废墟边缘，眼前是一座死寂的城市。"
char_count: 18
speed: 3.5 字/秒
estimated_duration: 18 / 3.5 = 5.1 秒
```

### 3.4 Output: Voiceover Timing Table

| Line# | Voiceover Text | Char Count | Speed | Duration | Emotional Tone |
|-------|---------------|-----------|-------|----------|----------------|
| 1 | 他站在废墟边缘 | 6 | 3.5 | 1.7s | 孤独、震撼 |
| 2 | 眼前是一座死寂的城市 | 9 | 3.5 | 2.6s | 压抑 |
| 3 | 三年前，这里还是他的家 | 10 | 3.0 | 3.3s | 回忆、温情 |

---

## 4. Panel Mapping

### 4.1 Map voiceover lines to image panels

Rules:

- One voiceover line → one panel. If the line is under 3 seconds, the same image can extend into the next beat.
- If a line exceeds 15 characters or 5 seconds → split into two panels: panel A (setup) + panel B (emphasis).
- Key emotional beats get their own panel even if the voiceover is short.
- Silent beats (no voiceover, pure atmosphere) need 2-4 second panels with ambient sound.

### 4.2 Define panel content

For each panel, specify:

- **Scene**: which location (from scene bible)
- **Character(s)**: who is in frame, their state/costume variant
- **Composition**: what the viewer sees (close-up on face, wide shot of environment, over-the-shoulder, detail insert)
- **Character expression/pose**: concrete visual — "eyes narrowed, hand gripping the railing" not "feeling determined"
- **Key prop or detail**: what must be visible (glove, weapon, screen, scar, etc.)
- **Lighting note**: scene-consistent or special (backlit, scanner glow, shadow cover)
- **Adjacent panel relationship**: how this panel connects to and differs from the previous one

### 4.3 Output: Panel Mapping Table

| Panel# | Line# | Scene | Characters | Composition | Expression/Pose | Key Props | Lighting | Adjacent Relation |
|--------|-------|-------|------------|-------------|-----------------|-----------|----------|-------------------|
| 1 | 1 | S1 废墟边缘 | 主角林骁 | 中景，侧后方 | 站立不动，肩膀微沉 | 背包、护目镜 | 阴天冷光，无阴影 | 开场，建立场景和主角 |
| 2 | 2 | S1 废墟边缘 | 主角林骁 | 切到正面近景 | 抬眼看向远方，喉结微动 | 无 | 冷光从右侧打脸 | 从身体进入表情，引导观众看眼神 |
| 3 | 3 | S2 回忆街道 | 主角(回忆)+家人 | 中景 | 微笑，眼神温暖 | 老式路灯、店铺招牌 | 暖黄昏光 | 闪回，色调从冷变暖 |

---

## 5. Batch Image Prompt Generation

### 5.1 Build the shared style prefix

Extract from the style bible. Example:

```text
写实电影风格，胶片颗粒感，高对比度，冷蓝主色调点缀琥珀色光，浅景深，暗部保留细节，科幻质感，自然光影，8K
```

This prefix is applied to every prompt in the project.

### 5.2 Prompt template for each panel

```text
[style_prefix]。[scene description]，[composition]，[character(s) description and expression]，[key props visible]，[lighting details]，[special quality]。

参考图：@图片X（[用途]），@图片Y（[用途]）
```

Apply the "只写变化，不重复参考图已有内容" principle.

### 5.3 Prompt generation rules

- Every character reference image is cited: "以 @图片1 中的林骁为人物参考"
- Scene references are cited: "场景参考 @图片4 的废墟城市布局和色调"
- The style prefix is prepended; do not add conflicting style keywords in the panel-specific part
- If two characters are in the same panel and each has a separate reference image, include both
- If a character has a different costume/state variant, reference the variant image and note the change
- Avoid negatives; use positive directional language

### 5.4 Output: Batch Image Prompt Table

| Panel# | Prompt | Reference Images | Notes |
|--------|--------|-----------------|-------|
| 1 | 写实电影风格...他站在灰色废墟边缘，中景侧后方构图，黑色作战服，背包，护目镜挂在领口，阴天漫射光，无强阴影，气氛压抑。 | @图片1 林骁 @图片4 S1废墟 | 开场，不需要表情细节 |
| 2 | 写实电影风格...从正面近景拍摄，他抬眼看向远方，眼神聚焦但克制，喉结微动，冷光从右侧偏上照亮半张脸，背景虚化。 | @图片1 林骁 @图片4 S1废墟 | 和Panel1衔接，切到近景 |
| 3 | 写实电影风格...暖黄昏光下的老街，两侧店铺亮着灯，林骁(回忆版)微笑走在家门口，身边有模糊的家人剪影，逆光。 | @图片1 林骁(回忆) @图片5 S2老街 | 闪回段，色调要暖 |

### 5.5 Import to 即梦

The user pastes each prompt into 即梦 with the specified reference images. Recommended settings:

- Aspect ratio: 16:9 for main version (can crop to 9:16 later)
- Quality mode: high detail
- Seed: use a fixed seed per character/scene combo when available for extra consistency
- Generate 2-3 variants per panel and select the best before assembly

---

## 6. Camera Motion Assignment

### 6.1 Motion type selection

Only 4 motion types used in motion comic mode. Assign by emotional function:

| Motion | Emotion/Function | Best For |
|--------|-----------------|----------|
| **Push-in** (缓慢推进) | 进入内心、强调、专注、压迫 | 重要对话、角色决定、关键道具、情绪转折 |
| **Pull-out** (缓慢拉开) | 释放、孤独、结束、全景 | 场景定场、闪回结束、结局、揭示环境全貌 |
| **Pan** (横移) | 场景展示、过渡、穿越 | 环境环境、人群穿越、车队行驶、长段独白 |
| **Zoom** (缩放) | 强调细节、反转、冲击 | 道具特写、信息揭示、表情从远景切到近景的冲击 |

### 6.2 Assignment rules

- Default motion: push-in at 80% speed. It's the safest and most cinematic.
- Do not assign motion just for variety. Every motion must serve the emotional beat.
- Adjacent panels should not use the same motion type unless it's intentional (e.g., three consecutive push-ins building intensity).
- When voiceover tone shifts (e.g., from narration to dialogue), the motion can shift to mark the transition.

### 6.3 Output: Motion Assignment Table

| Panel# | Duration | Motion Type | Motion Speed | In 剪映 |
|--------|----------|-------------|-------------|---------|
| 1 | 2.5s | 缓慢推进 | 80% | 缩放：起始100% → 结束110%，缓入缓出 |
| 2 | 3.0s | 无（静止） | - | 不添加关键帧，保持静止画面 |
| 3 | 3.5s | 缓慢横移 | 60% | 位置：起始左0 → 结束左-5%，缓入缓出 |

---

## 7. 剪映 Assembly Guide

### 7.1 Timeline structure

剪映 timeline should be organized as:

```
Track 1 (Video): Image panels with keyframe animations
Track 2 (Audio - Voiceover): TTS or voice recording clips
Track 3 (Audio - Ambience): Background atmosphere per scene
Track 4 (Audio - Effects): Key sound effects
Track 5 (Audio - Music): Background music
Track 6 (Text): Subtitles (optional)
```

### 7.2 Per-panel assembly

For each panel in剪映:

1. Import the generated image into Track 1
2. Set duration = voiceover line duration + 0.3-0.5s transition buffer
3. Add keyframe animation per the motion assignment table:
   - Push-in: Start scale=100%, End scale=110-120%, ease-in/ease-out
   - Pull-out: Start scale=110%, End scale=100%, ease-in/ease-out
   - Pan: Start position=X, End position=X-offset, ease-in/ease-out
   - Zoom: Start scale=100%, End scale=130-150%, linear or ease-in
4. Add transition between panels: 0.2-0.4s cross dissolve (default), or 0.5-0.8s for scene changes

### 7.3 Pacing adjustment rules

- If the assembled timeline feels rushed → add 0.3-0.5s of "reaction hold" after key emotional lines
- If the timeline drags → tighten transitions to 0.1-0.2s and reduce buffer to 0.2s
- For flashback or dream sequences → add a 0.5-1s white flash or blur transition
- For time jumps → hard cut (no transition), the contrast in image content does the work

### 7.4 Output: Assembly Table

| Track | Panel# | Asset | Timeline Start | Duration | Animation | Transition |
|-------|--------|-------|---------------|----------|-----------|------------|
| V1 | 1 | panel_001.png | 0:00.0 | 2.5s | Scale 100→110% (push-in) | 0.3s cross dissolve |
| V1 | 2 | panel_002.png | 0:02.8 | 3.0s | None | 0.3s cross dissolve |
| V1 | 3 | panel_003.png | 0:06.1 | 3.5s | Position left 0→-5% (pan) | 0.5s slow blur (scene change) |
| A1 | 1 | voiceover_line1.mp3 | 0:00.0 | 1.7s | - | - |
| A1 | 2 | voiceover_line2.mp3 | 0:02.5 | 2.6s | - | - |

---

## 8. Sound Plan

### 8.1 Voiceover (Track 2)

Options (from simplest to best quality):

1. **AI TTS** — 剪映自带配音 or 第三方 TTS. Fastest option. Choose voice that matches character.
2. **Human recording** — Best quality. Record after rough cut to get timing right.
3. **Hybrid** — TTS for rough cut, replace with human recording for final.

### 8.2 Ambience (Track 3)

Every scene needs ambience. No scene should be silent.

| Scene | Ambience |
|-------|----------|
| 废墟城市 | 风声穿过建筑、远处金属震颤 |
| 回忆街道 | 虫鸣、模糊的人声、老式路灯电流声 |
| 太空舱内 | 设备低频嗡鸣、气流声、按键音 |

### 8.3 Sound Effects (Track 4)

Key effects for important actions:

- Doors opening/closing
- Footsteps (surface-dependent)
- Equipment power-up, weapon charge, HUD beep
- Impact, crash, explosion (use sparingly)
- Nature: rain, wind, fire, water

### 8.4 Music (Track 5)

- Music enters only where emotion needs a lift: revelation, climax, grief, triumph
- Do not fill the entire runtime with music. Silence after a climax has more impact.
- Sci-fi recommendation: ambient synth pads, low bass pulses, minimal percussion
- Cut music into 15-30s segments that match scene boundaries, not one long track

### 8.5 Output: Sound Plan Table

| Scene | Panels | Ambience | Key SFX | Music | Notes |
|-------|--------|----------|---------|-------|-------|
| S1 废墟 | 1-2 | 风声、金属震颤 | 脚步踩碎石声 | 无 | 开场保持安静，只用环境声 |
| S2 回忆 | 3-4 | 虫鸣、模糊人声 | 门轴声、笑声 | 轻柔钢琴 | 闪回段用暖音色 |
| S3 控制室 | 5-7 | 设备低频嗡鸣 | 警报声、脚步声、按键音 | 低弦乐渐强 | 紧张段音乐从无到有 |

---

## 9. Production Sequence (For The User)

### Phase 1: Pre-production
1. Finalize script and voiceover timing.
2. Generate or prepare character reference images.
3. Generate or prepare scene reference images.

### Phase 2: Image generation
4. Generate all panel images in 即梦 using batch prompts.
5. Review panels for consistency. Reject and regenerate any that drift.

### Phase 3: Rough cut
6. Import panels into 剪映 in order.
7. Add scratch voiceover (TTS is fine for this stage).
8. Set panel durations to match voiceover timing.
9. Add keyframe animations per motion assignment.
10. Watch rough cut. Adjust pacing: does it drag? rush? miss beats?

### Phase 4: Polish
11. Replace scratch voiceover with final voiceover.
12. Add ambience tracks per scene.
13. Add sound effects at key moments.
14. Add music where emotion needs support.
15. Add subtitles if needed.
16. Final review and export.

---

## 10. Common Mistakes And How To Avoid Them

| Mistake | Fix |
|---------|-----|
| 面板文字过多，观众读图不过来 | 每条 voiceover 控制在 12 字以内，超过就拆面板 |
| 连续 3+ 个面板使用同一种构图 | 插入 reaction shot、细节特写、或换角度 |
| 角色在不同面板中"变脸" | 每张 prompt 引用相同角色参考图，确保 style prefix 一致 |
| 画面风格漂移 | 把所有 prompt 的 style prefix 统一；即使在即梦中选择不同的图生图方式 |
| 过渡生硬 | 场景变更时使用 0.5-0.8s 模糊过渡；同场景内用 0.3s 交叉溶解 |
| 声音空荡 | 每个场景至少铺一层环境音；不要留全静音段落 |
| 音乐铺满全片 | 音乐只在需要情绪抬升的地方进入；静音也是表达工具 |
