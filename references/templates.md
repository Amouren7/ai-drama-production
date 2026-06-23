# Templates

## Intake Questions

Use these as needed, not all at once:

```markdown
为了从 0 做成一部 AI 剧，我先确认 6 件事：
1. 你想做成什么形态：15s 概念片 / 60s 短片 / 3 分钟单集 / 多集短剧？
2. 类型和情绪是什么：悬疑、爱情、喜剧、古风、科幻、热血、治愈，还是其他？
3. 主角是谁，他/她最想得到什么？
4. 最大冲突是什么：敌人、秘密、误会、时间限制、身份困境？
5. 你希望视觉风格接近什么：写实电影、国漫、赛博朋克、古装剧、广告质感、暗黑童话等？
6. 你准备用哪些工具或素材：即梦/Seedance、已有图片、参考视频、音乐、角色设定？
7. 你更想走哪种制作路线：纯 AI 快速验证 / 参考图精修 / 多人协作 / 获奖短片级精剪？
```

## Final Markdown Skeleton

```markdown
# 《项目名》AI 剧制作方案

## 1. 项目简报
- 片名：
- 形式：
- 时长：
- 画幅：
- 目标平台：
- 受众：
- 类型：
- 核心卖点：
- 一句话故事：

## 2. 创作策略
- 观众 3 秒钩子：
- 稀缺性/传播点：
- 情绪曲线：
- 反转设计：
- MVP 测试方案：

## 3. 世界观设定
- 时间与地点：
- 社会/规则/技术系统：
- 日常质感：
- 视觉关键词：
- 不能漂移的设定：

## 4. 角色设定
| 角色 | 功能 | 外部目标 | 内在冲突 | 视觉锚点 | 弧光 |
|---|---|---|---|---|---|

### 角色参考图提示词
#### @图片1：角色名
```prompt
...
```

## 5. 场景与道具设定
| 场景/道具 | 剧情功能 | 氛围 | 视觉锚点 | 使用镜头 | 对应参考图 |
|---|---|---|---|---|---|

### 场景参考图提示词
```prompt
...
```

### 道具参考图提示词（每件道具一条，必须齐全）
#### @图片N：道具名
```prompt
...
```

## 6. 风格圣经
- 画面风格：
- 色彩：
- 光影：
- 镜头语言：
- 剪辑节奏：
- 声音设计：
- 禁止项：

## 7. 剧本结构
- 主题：
- 故事结构：
- 起：
- 承：
- 转：
- 合：
- 每 10-15 秒反转/悬念点：

## 8. 导演讲戏本
| 段落 | 时长 | 戏剧目的 | 画面讲戏 | 台词/声音 |
|---|---:|---|---|---|

## 9. 素材对应表
| 编号 | 类型 | 用途 | 备注 | 参考图提示词位置 |
|---|---|---|---|:---:|
| @图片1 | 角色 | xxx | xxx | §4 |
| @图片2 | 场景 | xxx | xxx | §5 |
| @图片3 | 道具 | xxx | xxx | §5 |

## 10. 分镜与视频提示词（单次生成，声音 inline）
### 10.1 提示词格式
每条提示词是一个完整的视频生成单位，画面+对白+音效+配乐在同一段文字中描述。用 `[对白]` `[音效]` `[配乐]` 在对应时间轴嵌入声音；不建立、不引用 `@音频`。

### 10.2 分镜与视频提示词
| 镜头 | 时长 | 视角 | 景别 | 引用视觉素材 | 动作节拍 | 表情/心理 | 前后镜关系 | 运镜 | 声音/对白处理 | 生成提示词 |
|---|---:|---|---|---|---|---|---|---|---|---|

## 11. 剧情逻辑与连贯性审查
### 成片模拟检查
- 剧情逻辑链（镜头因果、动机合理、对白与画面匹配）
- 场景连贯性（光照方向、角色位置、道具状态）
- 物理合理性（动作时间是否够用，多人互动视线是否匹配）
- 情绪弧线是否合理

## 12. 画面制作计划
- 核心场景锚点：
- 三视图角色资产：
- 需要垫图/参考图的镜头：
- 需要 PS/局部重绘/分层合成的镜头：
- 需要首尾帧的镜头：
- 需要画质放大/补帧的镜头：
- 需要分镜板图作为 @图片 参考注入的镜头：

## 13. 生成与剪辑计划
- 每条提示词生成次数：
- 备选镜头：
- 图片粗剪检查：
- 可剪辑点：
- 穿帮修复策略：
- 音画同步策略：

## 14. 声音与配乐计划
- 临时配音：
- 最终配音：
- 环境音：
- 拟音/音效：
- 配乐关键词：
- 音乐剪辑策略：

## 15. 审核清单
- 剧情：
- 视觉一致性：
- 分镜视角/景别：
- 节拍密度：
- 声音设计：
- 平台约束：
- 合规：

## 16. 封面设计与推广
### 封面图提示词
```prompt
...
```

### 话题标签
```
#标签1 #标签2 #标签3
```
```

## Character Reference Prompt Template

```prompt
Create a cinematic character design sheet for [character name], [age range], [role]. The image is split into two parts: left half is a detailed face close-up portrait; right half is a full-body turnaround showing front view, side view, and back view. Plain light background, consistent [visual style], [costume], [signature prop], [color palette], clear facial features, distinctive silhouette, production design quality, no text, no watermark.
```

## Visual Development Fields Template

```markdown
### [Character Name] Visual Development
- Story role:
- Commercial visual positioning:
- Gender / age / region:
- Height / body type / posture:
- One-line identity:
- Personality tags:
- Face: facial structure, eyes, brows, nose, lips, expression set
- Skin: tone, texture, realism level, imperfections
- Hair: style, color, volume, strand detail
- Costume: style, silhouette, layers, top/bottom/shoes, material, color blocking
- Accessories / signature props:
- Local detail anchors: hands, feet, waist, tattoo/scar, hair, jewelry, weapon/tool
- Palette: 3-5 dominant colors
- Forbidden drift: costume changes, hairstyle changes, plastic skin, extra characters, logo/watermark, distorted hands, conflicting style words
```

## Advanced Character Board Prompt Template

```prompt
Create an advanced cinematic character development board for [character name], [age range], [story role], in [visual style].

Layout in one image:
A area: left-side face close-up, showing clear facial structure, eyes, brows, lips, skin texture, hairline, and expression.
B area: center orthographic full-body turnaround of the same character: front view, side view, and back view, identical standing pose, identical costume, identical hairstyle, identical lighting, consistent proportions.
C area: right-side full-body scale view of the same character standing upright; include one simple vertical height marker only if needed.
D area: bottom local detail panels showing [hands/feet/hair/waist/tattoo/accessory/signature prop], each as a clean close-up.
E area: small color-card blocks showing the dominant palette, graphic blocks only.

Lighting: soft studio three-point lighting, clean shadows, consistent color temperature. Render quality: high-resolution production design sheet, detailed but not noisy, natural material texture, no wide-angle distortion.
Constraints: no dynamic pose changes, no alternate costume, no alternate hairstyle, no extra people, no logo, no watermark, no cluttered labels, no stylized cartoon drift, no plastic skin, no distorted hands, no floating props.
```

## Reference Image Extraction Prompt Templates

```prompt
Line-art extraction: Convert the uploaded reference image into clean black line art on a white background. Preserve and repair the subject's structure, patterns, costume ornaments, symbols, and missing details. Lines are clear, readable, and structurally complete.
```

```prompt
Flat color extraction: Based on the uploaded reference image, analyze its color construction and redraw it as a flat color draft. Keep the main color blocks, palette relationships, costume/prop color separation, and visual hierarchy clear.
```

```prompt
Reverse visual prompt: Deconstruct the uploaded reference image into reusable generation logic. Analyze subject, silhouette, composition, camera angle, style, materials, texture, palette, lighting, lens, mood, and quality controls. Output one concise professional Chinese prompt that can recreate this visual effect across image generation tools.
```

## Scene Grid Prompt Template

```prompt
Create a [3x3/3x4/4x4] cinematic environment reference grid for an AI drama in [style]. Each cell shows one empty location without characters, consistent color palette and lighting logic. Locations: [list locations]. Include architecture, props, atmosphere, camera-ready composition, clear spatial layout, no text, no watermark.
```

## Core Location Prompt Template

```prompt
Create a high-quality cinematic hero reference image for the main recurring location: [location name]. The location will appear in about [percentage] of the film, so the layout must be clear and reusable from multiple camera angles. Include [key props], [spatial layout], [lighting source and color], [mood], [style]. No main characters unless scale is needed, no text, no watermark.
```

## Seedance-Style Prompt Template — Single-Pass with Sound Inline

⚠️ **关键规则：视频提示词中声音必须 inline 嵌入。** 不要建立或引用 `@音频`，不要将对白/音效/配乐放在提示词之外的"音频备注"中。每一句对白、每一个音效、每一段配乐都必须在提示词的对应时间轴位置写好，用 `[对白]` `[音效]` `[配乐]` 标记。这样才能在 Seedance/即梦中实现音画同步生成。

每条提示词是一个"单次生成"单位：在一个镜头中，画面变化 + 对白 + 音效 + 配乐都在同一条提示词里描述。不需要先出图再出视频，直接一条提示词生成视频。

```prompt
以 @图片1 中的[角色]为主角，场景参考 @图片2 的[场景用途]。生成 [时长]，[画幅]，[风格]。

——以下描述动态变化和声音——

0-3 秒：[动作/情绪描述]
     [音效：环境音/效果音]
3-7 秒：[动作发展]
     [对白：角色台词内容]
7-12 秒：[转折或高潮]
     [对白：台词] [音效：效果音]
12-15 秒：[收束]
     [配乐：音乐描述]

镜头语言：...
结尾：动作自然收住。
```

**引导提示（仅作参考，不需要单独出图）：**
- 如果生图发现构图不对，可以修改提示词中的位置/角度描述后重新生成
- 视频生成前建议用角色参考图 @图片 锁定形象，用场景参考图锁定环境

## Sound Inline Rule

Film-mode video prompts do not use separate sound material prompts or sound reference tables. Put dialogue, sound effects, ambience, and music cues directly into the time-coded shot prompt with `[对白]` `[音效]` `[配乐]`.

## Repair Prompt Template

```markdown
上一版问题：
- 身份漂移：
- 动作过密：
- 运镜不清：
- 情绪不足：
- 声音缺失：

重写策略：
- 保留：
- 删除：
- 加强：
- 添加声音 inline：

新版提示词：
...
```

## Still Rough-Cut Checklist Template

```markdown
图片粗剪检查：
- 镜头顺序是否看得懂：
- 景别是否有变化：
- 对话场景是否有正反打/关系镜头/反应镜头：
- 主观视角和第三视角是否清楚：
- 台词时长是否需要补镜头：
- 哪些镜头先不要出视频：
- 哪些镜头必须重画或补图：
```

## Music Prompt Template

```prompt
Mysterious cinematic score for [scene purpose], [genre/style], gradually building tension, subtle electronic texture, flowing pulse, restrained percussion, elegant suspense, rising toward a reveal, no vocals, suitable for a short film scene.
```

## Sound-Inline Prompt Examples

### Good — sound inline in the prompt itself:
```prompt
0-2秒：阿凯低头看手机，拇指滑动屏幕。手机连续弹出消息。
     [音效：群消息提示音×5，密集快速]
2-3秒：阿凯抬头，嘴唇微动。
     [对白：阿凯——"不是，谁把集合点发到墨西哥了？"
      音效：背景远处引擎怠速声]
```

### Bad — sound as a separate note:
```prompt
0-2秒：阿凯低头看手机...
（音频备注：加群消息音效和对白）
```

## 剧情逻辑与环境连贯性自查清单

在生成视频之前，先在脑中模拟一遍成片效果，逐项检查：

```markdown
## 成片模拟检查

### 1. 剧情逻辑链
- [ ] 每个镜头是否由上一个镜头自然引导而来？
- [ ] 角色的每个动作是否有合理动机？
- [ ] 对白和画面动作是否匹配？（不能说"我加油"的同时在玩手机）
- [ ] 因果关系链是否清晰？A导致B，B导致C
- [ ] 观众能否不看字幕就理解发生了什么？

### 2. 场景连贯性
- [ ] 同一场景中的光照方向在所有镜头中是否一致？
- [ ] 角色位置关系是否跨镜头保持稳定？（A在左B在右）
- [ ] 道具状态是否连贯？（杯子在镜头1是满的，镜头2不能突然是空的）
- [ ] 角色服装和外观是否在相邻镜头中一致？
- [ ] 场景切换是否有明确的空间逻辑？

### 3. 物理合理性
- [ ] 角色动作在给定时间内是否能完成？
- [ ] 摄像机运动是否物理可实现？
- [ ] 多个角色互动时，视线方向是否正确？

### 4. 情感弧线
- [ ] 情绪曲线是否合理递进？
- [ ] 反转/笑点/泪点是否有足够铺垫？

### 发现问题后的操作
- 逻辑不通 → 重写该段分镜，确保因果关系清晰
- 动作不合理 → 延长镜头时长或拆分动作
- 对白与画面不匹配 → 修改对白或修改动作描述
- 场景跳变 → 添加过渡镜头或统一场景描述
```

## Cover / Thumbnail Design Prompt Template

为每部短片设计一张封面图。封面是静态图，捕捉全片最具代表性的瞬间，上方或下方预留标题文字空间。

```prompt
Create a cinematic thumbnail for a comedy short film titled "[标题]", 9:16 vertical. [最核心的视觉描述：角色在做什么、表情如何、关键道具]. [场景氛围描述]. [画面构图说明，包括文字位置]. High quality, filmic, eye-catching for social media feed, no text watermark, leave [上方/下方] space for title text overlay.
```

**规则：**
- 使用与视频一致的 `@图片` 角色/场景参考图，保持视觉一致性
- 画面构图要预留标题文字空间（上方或下方留空/纯色/渐变区域）
- 捕捉全片最具传播力的那一个瞬间（笑点/反转/名场面）
- 封面上的标题文字后期添加（PS/剪映加字），不在生图中生成文字
