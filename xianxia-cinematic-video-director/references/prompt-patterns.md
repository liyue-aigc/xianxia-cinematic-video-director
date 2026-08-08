# Input and output patterns

## Minimal input

```text
核心故事：一名旅人在崖畔等待同伴，最终二人共同走向天宫
总时长：30秒（省略时默认）
画幅比例：16:9（省略时默认）
空间尺度强度：史诗级（省略时默认）
饱和策略：选择性高饱和（省略时默认）
节奏：庄严舒缓（省略时默认）
输出模式：标准
```

## Advanced input

```text
总时长：30秒
画幅比例：21:9
镜头数量：6
节奏：庄严舒缓
核心故事：等待 -> 发现 -> 同行 -> 抵达
起点：崖畔苍松下的白玉平台
路径：悬空长桥
终点：云海尽头的巨型天门
人物：两名虚构成年旅人，月白与孔雀青长衣，背影为主
视觉锚点：横跨天际的朱红与白玉天门
空间尺度强度：超宏大
饱和策略：选择性高饱和
主色：天青、月白、松绿；朱红和暖金局部强调
光线：清晨右侧低角度侧逆光
镜头偏好：缓慢横移揭示、跟随、最终远景停留；不要快速推拉
输出模式：标准
```

## Standard shot table

```text
| 镜头 | 时间 | 时长 | 功能 | 景别/镜头 | 主运动 | 结束状态 |
|---|---|---:|---|---|---|---|
| 01 | 00:00–00:05 | 5s | 世界揭示 | 极远景 / 28mm | 横向视差揭示 | 人物和远处天门同时可见 |
```

## Per-shot prompt pattern

```text
Shot <number>, <duration>, <ratio>.
Function: <one shot function>.
Initial composition: <stable first frame, scale relationship, lens and framing>.
Subject action: <one readable action chain and gaze/travel target>.
Camera movement: <one move, direction, speed, extent; explicitly prohibit incompatible moves>.
Environmental motion: <one or two restrained layers>.
End state: <stable last-frame composition and newly revealed information>.
Continuity invariants: <character, landmark, geography, light, palette, weather>.
Avoid: <shot-specific geometry, identity, motion, and color failures>.
```

## Compact 30-second spine example

Story: `等待 -> 察觉 -> 相遇 -> 同行 -> 仰望 -> 共同赴天宫`.

| Shot | Duration | Function | Direction |
|---|---:|---|---|
| 01 | 5s | World reveal | lateral parallax through a giant pine; show person and distant gate |
| 02 | 4s | Human scale | slow pullback from sleeve and profile silhouette to cliff platform |
| 03 | 5s | Discovery | gaze-matched cut; second traveler appears along the suspended bridge |
| 04 | 5s | Traversal | stable tracking follow as both walk toward the same destination |
| 05 | 4s | Scale escalation | low-angle tilt from tiny travelers to off-frame heavenly gate |
| 06 | 7s | Resolution | wide pullback and settle; hold both travelers beneath the immense gate |

The example supplies rhythm, not mandatory imagery. Change setting, actions, and landmark to match the user.

## Global negative-constraint pattern

```text
No unrelated location changes, character duplication, outfit drift, face drift, landmark redesign, changing roof count, reversed bridge direction, sun-direction change, palette drift, random weather reset, or geography discontinuity.

No rapid montage in majestic mode, no shot shorter than 3 seconds without intent, no identical push-in on every shot, no simultaneous pan + zoom + orbit + roll, no fast camera shake, no random speed ramps, no unstable first or last frame.

No melting architecture, sliding columns, boiling ornament, morphing carvings, broken perspective, fisheye distortion, rubber limbs, duplicated hands, floating garments without wind logic, or clouds moving in conflicting directions.

No global orange-gold wash, equal-intensity saturated colors, neon clouds, crushed black shadows, gray fog that erases the destination, plastic jade, excessive gilding, text, subtitles, logos, or watermarks.
```

