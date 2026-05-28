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
| 场景/道具 | 剧情功能 | 氛围 | 视觉锚点 | 使用镜头 |
|---|---|---|---|---|

### 场景宫格图提示词
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
| 编号 | 类型 | 用途 | 备注 |
|---|---|---|---|

## 10. 分镜与 Seedance 提示词
| 镜头 | 时长 | 视角 | 景别 | 引用素材 | 动作节拍 | 表情/心理 | 前后镜关系 | 运镜 | 音频 | 生成提示词 |
|---|---:|---|---|---|---|---|---|---|---|---|

## 11. 画面制作计划
- 核心场景锚点：
- 三视图角色资产：
- 需要垫图/参考图的镜头：
- 需要 PS/局部重绘/分层合成的镜头：
- 需要首尾帧的镜头：
- 需要画质放大/补帧的镜头：

## 12. 生成与剪辑计划
- 每条提示词生成次数：
- 备选镜头：
- 图片粗剪检查：
- 可剪辑点：
- 穿帮修复策略：
- 音画同步策略：

## 13. 声音与配乐计划
- 临时配音：
- 最终配音：
- 环境音：
- 拟音/音效：
- 配乐关键词：
- 音乐剪辑策略：

## 14. 审核清单
- 剧情：
- 视觉一致性：
- 分镜视角/景别：
- 节拍密度：
- 声音设计：
- 平台约束：
- 合规：
```

## Character Reference Prompt Template

```prompt
Create a cinematic character design sheet for [character name], [age range], [role]. The image is split into two parts: left half is a detailed face close-up portrait; right half is a full-body turnaround showing front view, side view, and back view. Plain light background, consistent [visual style], [costume], [signature prop], [color palette], clear facial features, distinctive silhouette, production design quality, no text, no watermark.
```

## Scene Grid Prompt Template

```prompt
Create a [3x3/3x4/4x4] cinematic environment reference grid for an AI drama in [style]. Each cell shows one empty location without characters, consistent color palette and lighting logic. Locations: [list locations]. Include architecture, props, atmosphere, camera-ready composition, clear spatial layout, no text, no watermark.
```

## Core Location Prompt Template

```prompt
Create a high-quality cinematic hero reference image for the main recurring location: [location name]. The location will appear in about [percentage] of the film, so the layout must be clear and reusable from multiple camera angles. Include [key props], [spatial layout], [lighting source and color], [mood], [style]. No main characters unless scale is needed, no text, no watermark.
```

## Seedance-Style Prompt Template

```prompt
以 @图片1 中的[角色]为主角，场景参考 @图片2 的[场景用途]，参考 @视频1 的[运镜/动作/节奏用途]。生成 [时长] 秒，[画幅]，[风格]。

0-3 秒：...
3-7 秒：...
7-12 秒：...
12-15 秒：...

镜头语言：...
角色动作与情绪：...
台词/声音：...
结尾：动作自然收住，保留情绪余韵。
```

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
- 降低节拍：

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
