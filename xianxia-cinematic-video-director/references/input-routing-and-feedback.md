# Input routing and feedback

## First-pass classification

Classify the input before directing. Do not expose a long checklist; output only feedback that helps the user act.

| State | Signals | Response |
|---|---|---|
| 可直接导演 | Has a scene, subject/action, or visible spatial relationship | Direct immediately |
| 信息较少但可补全 | A mood, still-image prompt, or one-line idea with no camera terms | State 1–3 inferred defaults, then propose motion |
| 请求帮助 | “怎么运镜”, “不会写”, “帮我选”, “有什么手法”, “给案例” | Load the help/examples reference; give a formula and scene-specific sample |
| 运镜冲突 | Simultaneous incompatible moves, impossible distance/framing, conflicting directions/speeds | Name the conflict, visible consequence, and closest corrected version |
| 非运镜但属仙侠视频 | Costume, dialogue, plot, or still-image content without temporal/camera intent | Separate usable visual facts from missing motion; translate into a camera-ready request |
| 完全无关 | No meaningful connection to video, camera, visual sequence, or xianxia direction | State scope and give 1–2 relevant rewrite examples |

## Helpful feedback format

Use only the rows needed:

```text
输入状态：可直接用 / 可补全 / 存在冲突 / 不属于本 Skill
我理解到的有效内容：<scene, subject, action, mood, space>
需要修正：<exact phrase and why it fails on screen>
修正版：<copy-ready camera instruction>
采用的默认补充：<only assumptions that materially affect the result>
```

Do not scold, dump theory, or ask for every missing parameter. If a safe, reversible assumption works, label it and continue.

## Common camera-prompt errors

### No camera movement at all

Input: `月下白衣剑仙站在天门前。`

Feedback: The image is usable, but it lacks subject change, camera purpose, speed, path, and end composition. Infer a calm/tense/emotional intent from nearby context. If none exists, offer two distinct routes:

- scale route: start behind the person, pull back and rise to reveal the heavenly gate;
- emotional route: locked medium-wide frame, only sleeves and cloud move, holding the decision.

### Too many simultaneous moves

Input: `镜头快速推进，同时拉远、360度环绕、升空、翻滚并摇镜。`

Feedback: Push and pull contradict; orbit, rise, roll, and pan compete for orientation. The likely result is unstable geometry and unreadable action. Convert it into ordered phases:

```text
0–1s locked anticipation; 1–3s fast push toward the swordsman; 3–5s continue into a 90-degree arc and crane slightly upward; decelerate into a stable wide frame. No pullback, roll, or extra pan.
```

### Physically impossible framing change

Input: `镜头只前进10厘米，从眼睛特写变成整座万里仙城极远景。`

Feedback: A tiny forward move cannot produce a huge pullback reveal. Preserve the intended scale surprise by changing the path:

```text
Begin on the eye reflection; rapidly pull back 20–30 meters while craning upward, or cut on the reflection to an aerial extreme-wide view of the immortal city.
```

### Ambiguous speed

Input: `镜头有感觉地运动，做得震撼一点。`

Feedback: “有感觉/震撼” does not define visible motion. Translate it into purpose and curve:

```text
Hold 0.5s on the silent figure, accelerate forward along the bridge for 2.5s, pass the figure, then crane upward and decelerate for 2s as the giant gate fills the upper frame.
```

### Non-camera content

Input: `帮我写一篇职场邮件。`

Response: `这个 Skill 专门处理东方仙侠视频的分镜与运镜，不适合写职场邮件。你可以改为：“仙门议事殿中，两位长老对峙，帮我设计一组压迫感运镜。”`

## When to ask a question

Ask at most one high-impact question only when different answers would materially change the plan, such as “想要静谧情绪还是高速追逐？” Otherwise give a recommended route plus alternatives and continue.
