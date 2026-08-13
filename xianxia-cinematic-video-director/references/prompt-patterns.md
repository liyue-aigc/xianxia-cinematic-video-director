# Input and output patterns

## Minimal input

```text
核心场景：一名剑修穿过竹林，察觉身后追兵后御剑冲出峡谷
总时长：15秒（省略时默认30秒）
画幅比例：16:9（省略时默认）
节奏：叙事自适应（省略时默认）
输出模式：标准
```

## Advanced input

```text
总时长：30秒
画幅比例：21:9
镜头数量：7
节奏：紧张史诗
运镜强度：强动势，但建筑必须稳定
核心故事：潜行 -> 察觉 -> 追逐 -> 反击 -> 脱身 -> 望见天门
起点：雨夜竹林石阶
路径：狭窄峡谷与悬空索桥
终点：云海尽头的巨型天门
人物：一名虚构成年剑修，月白长衣，右手持剑
视觉锚点：朱红与白玉天门
光线：右后方冷月光；剑光仅作青色局部强调
镜头偏好：低位跟拍、静机位掠过、一次俯冲航拍；结尾落稳
禁用：全程慢推、随机旋转、建筑形变
输出模式：标准
```

## Standard shot table

```text
| 镜头 | 时间 | 时长 | 功能 | 景别/焦段 | 运镜目的 | 运镜阶段 | 速度曲线 | 结束状态 |
|---|---|---:|---|---|---|---|---|---|
| 01 | 00:00–00:04 | 4s | 建立威胁 | 低位广角 / 28mm | 用速度反差表现追兵逼近 | 静机位，人物由远及近掠过前景 | 静止相机 + 快速主体 | 追兵剑光进入画面深处 |
```

## Per-shot prompt pattern

```text
Shot <number>, <duration>, <ratio>.
Function: <one shot function>.
Initial composition: <stable first frame, scale relationship, lens and framing>.
Subject action: <one readable action chain and gaze/travel target>.
Motion purpose: <what the camera movement makes the viewer feel or learn>.
Camera choreography: <one dominant move or ordered phases with direction, speed curve, extent, and timing; prohibit incompatible simultaneous moves>.
Environmental motion: <one or two restrained layers>.
End state: <stable last-frame composition and newly revealed information>.
Continuity invariants: <character, landmark, geography, light, palette, weather>.
Avoid: <shot-specific geometry, identity, motion, and color failures>.
```

## Compact 30-second adaptive spine example

Story: `潜行 -> 暴露 -> 追逐 -> 失衡 -> 反击 -> 脱身 -> 远望天门`.

| Shot | Duration | Function | Camera energy |
|---|---:|---|---|
| 01 | 5s | Establish rainy bamboo geography | crane fall at medium-slow speed, then hold |
| 02 | 3s | Reveal pursuit | locked low frame; swordsman and pursuers cross at high speed |
| 03 | 4s | Pursuit | accelerating trailing track through the path |
| 04 | 3s | Near-fall | short controlled handheld and downward tilt; abrupt stop |
| 05 | 4s | Counterattack | 120-degree arc track timed to one sword sweep |
| 06 | 4s | Escape | aerial rise following the sword flight, medium-fast to slow |
| 07 | 7s | Destination reveal | pullback reveal, decelerate, hold the heavenly gate for 2 seconds |

This example demonstrates an energy curve, not mandatory imagery. Change movement families when the story requires stillness, dialogue, ritual, romance, horror, or scale discovery.

## Global negative-constraint pattern

```text
No unrelated location changes, character duplication, outfit or face drift, landmark redesign, reversed bridge direction without an axis reset, sun-direction change, palette drift, random weather reset, or geography discontinuity.

No identical movement on every shot, no universal slow push, no unjustified speed ramp, no simultaneous pan + zoom + orbit + roll + crane, no unreadable horizon, no random shake, and no unstable first or last frame.

No melting architecture, sliding columns, boiling ornament, morphing carvings, broken perspective, fisheye distortion, rubber limbs, duplicated hands, floating garments without wind logic, or conflicting cloud directions.

No global orange-gold wash, equal-intensity saturated colors, neon clouds, crushed shadows, destination-erasing fog, plastic jade, excessive gilding, text, subtitles, logos, or watermarks.
```
