# Motion Comic Templates

## Intake Questions For Motion Comic Mode

Use these to quickly determine if the project fits motion comic mode:

```markdown
为了帮你做一部真人/科幻质感的漫剧，我先确认几件事：

1. 你目前有什么素材？
   - 已有完整剧本 / 故事大纲 / 只有想法
   - 已有角色设计图
   - 已有场景参考图

2. 你希望多长？
   - 30-60s 概念短片 / 1-3 分钟单集 / 多集系列

3. 类型和视觉风格是什么？
   - 真人质感科幻 / 真人质感现实题材 / 其他
   - 参考电影或作品风格（如《流浪地球》《银翼杀手》《黑镜》）

4. 旁白形式？
   - 纯旁白叙事（第三人称）
   - 角色对白 + 旁白混合
   - 纯画面+音乐（无旁白）

5. 你的工具链？
   - 即梦 / 即梦 + 剪映 / 其他

6. 你希望什么节奏产出？
   - 快速：1-2 天出一个可看版本
   - 精修：多次迭代，3-7 天
```

---

## Markdown Skeleton (Motion Comic)

```markdown
# 《项目名》AI 漫剧制作方案

## 1. 项目简报
- 片名：
- 形式：AI 漫剧（即梦出图 + 剪映装配）
- 目标时长：
- 画幅：
- 目标平台：
- 核心受众：
- 类型/风格：
- 一句话故事：
- 视觉风格参考：

## 2. 创作策略
- 观众 3 秒钩子：
- 情绪路线：
- 核心反转/记忆点：
- 核心动作母题（重复出现的视觉主题）：

## 3. 世界观设定
- 时间与地点：
- 社会/规则/技术系统：
- 日常质感与氛围：
- 视觉关键词：
- 不可漂移的核心设定：

## 4. 角色设定
| 角色 | 年龄 | 功能 | 外部目标 | 内在冲突 | 服装/道具 | 视觉锚点 |
|------|------|------|---------|---------|----------|---------|

### 角色参考图提示词
以 @图片X 命名

## 5. 场景与道具设定
| 场景/道具 | 剧情功能 | 氛围 | 光线特征 | 视觉锚点 |
|----------|---------|------|---------|---------|

### 场景参考图提示词

## 6. 风格圣经
- 画面质感：
- 主色调与配色逻辑：
- 光影特征：
- 镜头语言（标准漫剧 4 种运镜）：
- 禁止漂移项：

## 7. 统一 Style Prefix
将此前缀用于所有出图 prompt：

```prompt
[自动生成的 style prefix]
```

## 8. 旁白脚本与时间线
| 行号 | 旁白文字 | 字数 | 语速 | 时长 | 情绪 |
|------|---------|------|------|------|------|

## 9. 分镜映射表
| 面板 | 旁白行 | 场景 | 角色 | 构图 | 表情/动作 | 关键道具 | 光线 | 前一面板关系 |
|------|--------|------|------|------|----------|---------|------|-------------|

## 10. 批量图生提示词
| 面板 | Prompt | 参考图 | 备注 |
|------|--------|--------|------|

## 11. 运镜分配表
| 面板 | 时长 | 运镜类型 | 速度 | 剪映关键帧设置 |
|------|------|---------|------|---------------|

## 12. 剪映装配表
| 轨道 | 面板 | 素材 | 起始时间 | 时长 | 动画 | 过渡 |
|------|------|------|---------|------|------|------|

## 13. 声音计划
| 场景 | 面板范围 | 环境音 | 音效 | 音乐 | 备注 |
|------|---------|--------|------|------|------|

## 14. 制作顺序
- Pre-production：
- 出图：
- 粗剪：
- 精修与导出：
```

---

## Panel Mapping Table Template

```markdown
| Panel# | Line# | Scene | Characters | Composition | Expression/Pose | Key Props | Lighting | Adjacent Relation |
|--------|-------|-------|------------|-------------|-----------------|-----------|----------|-------------------|
| 1 | 1 | | | | | | | |
| 2 | 2 | | | | | | | |
```

### Column guide

- **Panel#**: sequential, 1-based
- **Line#**: which voiceover line this panel serves
- **Scene**: scene/location identifier from the scene bible
- **Characters**: which characters appear and their variant state (normal/injured/回忆)
- **Composition**: wide/medium/close-up/insert + camera angle (eye-level/low-angle/over-the-shoulder/POV)
- **Expression/Pose**: concrete visible state — "攥紧车把，指节发白" not "紧张"
- **Key Props**: what objects must be clearly visible
- **Lighting**: scene baseline or special instruction — "冷光，从右侧45度打脸，左脸在阴影中"
- **Adjacent Relation**: how this panel differs from the previous one — "从远景切到近景，揭示表情"

---

## Batch Image Prompt Template

### Structure

```prompt
[Style Prefix]。[Scene Description]，[Composition Description]，[Character(s) Description and Action/Expression]，[Key Props Visible]，[Lighting Notes]，[Color Notes]。

参考图：@图片X（[角色/场景]参考），@图片Y（[角色/场景]参考）
```

### Example

```prompt
写实电影风格，胶片颗粒感，高对比度，冷蓝主色调点缀琥珀色光，浅景深，暗部保留细节，科幻质感，自然光影，8K。灰铁色的控制室内部，冷白顶灯照射，金属表面反射低光斑。主角林骁站在控制台前，从侧后方中景拍摄，他身体微前倾，右手悬停在键盘上方但没有按下，眼神集中在屏幕数据上。后颈能看到一条旧疤痕。背景中三个工作站的屏幕亮着琥珀色数据流。

参考图：@图片1 林骁角色参考，@图片4 控制室场景参考
```

### Rules

- Style prefix goes first. Never add conflicting style keywords in the body.
- Reference images: max 3-4 per prompt. Always state the purpose of each.
- Write only what changes or what the reference images cannot capture.
- Always specify character expression as visible action, not internal emotion.

---

## Motion Assignment Template

```markdown
| Panel# | Duration | Motion Type | Motion Speed | 剪映 Keyframe Setting |
|--------|----------|-------------|-------------|----------------------|
| 1 | 3.0s | push-in | 80% | Scale: 100% → 112%, ease-in/ease-out |
| 2 | 2.5s | none | - | No keyframes |
| 3 | 4.0s | pan-left | 60% | Position: 0 → -8%, ease-in/ease-out |
| 4 | 3.0s | zoom | 70% | Scale: 100% → 145%, linear |
| 5 | 3.5s | pull-out | 80% | Scale: 110% → 100%, ease-in/ease-out |
```

### Motion presets for 剪映

**Push-in (缓慢推进):**
```
起始缩放: 100% (关键帧A)
结束缩放: 110-120% (关键帧B)
时长: 匹配面板时长
曲线: 缓入缓出
```

**Pull-out (缓慢拉开):**
```
起始缩放: 110-115% (关键帧A)
结束缩放: 100% (关键帧B)
时长: 匹配面板时长
曲线: 缓入缓出
```

**Pan (横移):**
```
起始位置: 0% (关键帧A)
结束位置: -5-8% (关键帧B)
时长: 匹配面板时长
曲线: 缓入缓出
```

**Zoom (缩放强调):**
```
起始缩放: 100% (关键帧A)
结束缩放: 130-150% (关键帧B)
时长: 面板时长的 50-60%（后半段开始缩放到结束）
曲线: 线性
```

---

## 剪映 Assembly Table Template

```markdown
## 时间线布局

### 轨道分配
- V1: 主画面（面板图片 + 关键帧动画）
- A1: 配音/旁白
- A2: 环境音
- A3: 音效
- A4: 背景音乐
- T1: 字幕（可选）

### 面板装配表
| 轨道 | 面板 | 素材文件 | 起始时间 | 时长 | 关键帧动画 | 过渡 | 备注 |
|------|------|---------|---------|------|-----------|------|------|
| V1 | 1 | panel_001.png | 00:00.0 | 3.0s | Scale 100→112% | 0.3s 交叉溶解 | |
| A1 | 1 | vo_001.mp3 | 00:00.0 | 2.8s | - | - | 旁白行1 |
```

### Default transition settings

| Transition Type | Duration | When To Use |
|----------------|----------|-------------|
| Cross dissolve | 0.2-0.3s | Default — between panels in the same scene |
| Blur (模糊) | 0.5-0.8s | Scene changes and time jumps |
| White flash | 0.3-0.5s | Flashback entry/exit, memory trigger |
| Hard cut | 0s | Action beats, sudden reversal, impact |
| Black fade | 0.5-1.0s | Beginning, ending, passage of significant time |

---

## Sound Plan Template

```markdown
| Scene | Panels | Ambience (A2) | Sound Effects (A3) | Music (A4) | Notes |
|-------|--------|--------------|-------------------|------------|-------|
| S1 废墟 | 1-3 | 风声穿建筑，金属震颤 | 脚步踩碎石，远处结构坍塌声 | 无 | 开场静默，只用环境建立空间 |
| S2 回忆 | 4-6 | 虫鸣，模糊市集人声 | 老式风扇声，笑声 | 轻柔钢琴，慢速琶音 | 暖色调场景，音乐轻入 |
| S3 控制室 | 7-10 | 设备低频嗡鸣，气流 | 键盘敲击，终端蜂鸣，脚步声 | 低弦乐 pad，渐强 | 紧张感积累 |

### Sound source recommendations

- Ambience: 剪映音效库 or freesound.org
- Sci-fi ambience: white noise filtered through EQ, slow LFO modulation
- Footsteps: match surface type (metal, concrete, dirt, snow)
- Music: Pixabay / Uppbeat (free), or AI-generated (Suno/udio), or剪映自带
```

---

## TTS Voice Selection Guide

```markdown
### 剪映配音角色建议

| 角色类型 | 推荐 TTS 声音 | 语速 | 语调 |
|---------|-------------|------|------|
| 深沉叙述 | 剪映「解说男声」或「深沉男声」 | 100-110% | 平直、沉稳 |
| 年轻男性 | 剪映「阳光男声」 | 105-115% | 正常略有起伏 |
| 女性叙述 | 剪映「温柔女声」或「知性女声」 | 100-110% | 自然起伏 |
| 科幻/AI 角色 | 剪映「机器音」或后期加 filter | 90-100% | 平直，减少语调变化 |
```

---

## Style Preset Templates

### 赛博朋克/科幻暗夜

```prompt
写实电影风格，高对比度，暗部深沉保留细节，冷蓝主色调，霓虹紫/品红点缀光，雨夜湿路面反射，浅景深，胶片颗粒，4K
```

### 末日废土

```prompt
写实电影风格，低饱和，灰黄/土褐色调，强阳光或阴天漫射光，尘土飘浮，粗砺质感，轻微褪色，浅景深，胶片颗粒，8K
```

### 太空科幻

```prompt
写实电影风格，冷白/冷蓝主色调，高对比硬光，金属表面反射，黑暗星空背景，屏幕光晕，干净线条，无颗粒，超高清，8K
```

### 近未来都市

```prompt
写实电影风格，中性色调偏冷，晴日/阴天自然光，玻璃幕墙反射，城市肌理，低饱和度，真实摄影质感，浅景深，4K
```

### 现实情感/文艺

```prompt
写实电影风格，低对比度，暖棕/奶油色调，柔和自然光，浅景深，轻微褪色，家庭摄影质感，温暖颗粒感，4K
```

---

## Per-Scene Emotion-To-Music Mapping

| Emotion | Music Style | Instrument | Tempo | Volume |
|---------|------------|------------|-------|--------|
| 孤独/空旷 | Ambient pad, long reverb | Synth pad, cello | 50-60 BPM | Low |
| 紧张/悬疑 | Low pulse, rising tension | Bass drone, sub bass | 70-90 BPM | Low-mid |
| 悲伤/回忆 | Slow piano, string swells | Piano, violin | 50-70 BPM | Mid |
| 决心/行动 | Percussive drive, brass | Drums, brass, synth | 100-120 BPM | Mid-high |
| 释放/高潮 | Full orchestra or synth wall | Full ensemble | 80-110 BPM | High |
| 和解/平静 | Soft guitar or piano, ambient | Acoustic guitar, piano | 60-70 BPM | Low-mid |
| 科幻/神秘 | Minimal synth, glitch | Synth, processed sounds | 70-90 BPM | Low-mid |
