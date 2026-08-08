---
name: xianxia-cinematic-video-director
description: Design, derive, optimize, and diagnose cinematic Eastern xianxia video concepts, story spines, shot lists, camera movement, pacing, continuity locks, keyframe prompts, and per-shot image-to-video prompts. Use when users request xianxia short videos, multi-shot storyboards, shot-by-shot generation prompts, first/last-frame plans, camera choreography, visual continuity, pacing corrections, reference-video diagnosis, or explicit direct video generation. Support 16:9, 21:9, 4:3, 3:2, 4:5, and 9:16; default to 30 seconds, 16:9, six majestic shots, epic scale, and selective high saturation when unspecified.
---

# Xianxia Cinematic Video Director

Turn a scene idea, image prompt, keyframe, or reference video into a coherent xianxia film sequence. Direct time, motion, shot progression, and cross-shot continuity; do not output a pile of unrelated beautiful images.

## Required loading order

1. Read [references/visual-baseline.md](references/visual-baseline.md) for every task.
2. Read [references/shot-grammar.md](references/shot-grammar.md) for storyboard creation, pacing, shot-count selection, or video diagnosis.
3. Read [references/continuity-and-motion.md](references/continuity-and-motion.md) for any multi-shot, reference-image, first/last-frame, camera-motion, or direct-generation task.
4. Read [references/prompt-patterns.md](references/prompt-patterns.md) when the user asks for complete prompts, examples, a full shot plan, or supplies an underspecified concept.

## Relationship to the image Skill

- Use this Skill for sequence structure, time, camera motion, continuity, and per-shot video prompts.
- Use `$xianxia-visual-director` for standalone stills or especially detailed first-frame/keyframe direction when it is explicitly invoked or available in the active task.
- Keep this Skill independently usable. Do not require the image Skill to complete a video plan.
- When both Skills are used, lock shared parameters once: ratio, scale intensity, saturation strategy, architecture, people, palette, materials, weather, and light direction.

## Operating modes

- **Create**: Expand a concept into a story spine, shot plan, continuity locks, and per-shot prompts.
- **Derive**: Keep the same world and continuity anchors while changing narrative beat, pacing, season, palette, or camera language.
- **Optimize**: Rewrite an existing storyboard or video prompt for stronger progression, controllable motion, and continuity.
- **Diagnose**: Inspect a reference video or shot list for weak scale, fast montage, repetitive framing, random motion, color drift, or identity drift, then provide a corrected plan.
- **First/last frame**: Design compatible start and end states with a physically plausible movement path between them.
- **Direct video**: Invoke an available video-generation capability only when the user explicitly requests generation or direct output. A storyboard or parameter block is never implicit authorization to generate paid media.

## Parameter lock

Record explicit values and label supplemented defaults.

- `画幅比例`: `16:9`, `21:9`, `4:3`, `3:2`, `4:5`, or `9:16`; default `16:9`.
- `总时长`: positive duration; default `30秒`.
- `镜头数量`: explicit value or derived from duration; default `6镜头` for 30 seconds.
- `节奏`: `庄严舒缓`, `流动叙事`, or `紧张史诗`; default `庄严舒缓`.
- `空间尺度强度`: `辽阔`, `史诗级`, or `超宏大`; default `史诗级`.
- `饱和策略`: `自然鲜明`, `选择性高饱和`, or `华丽高饱和`; default `选择性高饱和`.
- `核心故事`: what changes from beginning to end.
- `世界与地理`: location, spatial relationships, destination, and travel axis.
- `人物`: count, fictional adult identity, silhouette, wardrobe, action, and emotional state.
- `建筑/视觉锚点`: one main landmark and its invariant silhouette.
- `时间天气`: time of day, cloud, rain, fog, wind, and atmospheric evolution.
- `镜头语言`: lens family, camera height, movement, and transition preferences.
- `目标平台/模型`: generic when omitted; adapt only when named.
- `输出模式`: standard, concise, storyboard only, prompts only, diagnosis, or direct video.

If omitted, state: `画幅比例：16:9（默认补充）`, `总时长：30秒（默认补充）`, `镜头数量：6（默认补充）`, `节奏：庄严舒缓（默认补充）`, `空间尺度强度：史诗级（默认补充）`, and `饱和策略：选择性高饱和（默认补充）`.

## Direction workflow

1. **Lock the ending.** Define the final destination, reveal, decision, reunion, departure, or emotional resolution before arranging shots.
2. **Write one story spine.** Express the sequence as a single change, such as `等待 -> 发现 -> 同行 -> 抵达`.
3. **Build geography.** Fix where the character starts, where the landmark is, and how the travel path connects them.
4. **Choose shot count from duration.** Follow [references/shot-grammar.md](references/shot-grammar.md). Prefer fewer readable shots over rapid montage.
5. **Assign shot functions.** Each shot must perform one job: reveal world, locate person, show traversal, escalate scale, reveal landmark, or resolve emotion.
6. **Choreograph motion.** Give each shot one primary camera movement and one restrained environmental-motion layer. Avoid compound motion stacks.
7. **Lock continuity.** Form the continuity card before writing prompts. Repeat invariants in every per-shot prompt.
8. **Design key states.** Describe the initial frame, movement path, and end state. Use explicit first/last frames when the workflow supports them.
9. **Write per-shot prompts.** Order each as duration and ratio -> initial composition -> subject action -> camera movement -> environmental motion -> end state -> continuity invariants -> avoid.
10. **Audit the sequence.** Verify duration sum, shot diversity, motion plausibility, scale progression, visual continuity, color stability, destination clarity, and ending resolution.

## Core timing rules

- Default 30-second plan: six shots averaging 4–6 seconds.
- Reserve at least one 6–8 second hero establishing or final reveal shot in `庄严舒缓` mode.
- Avoid shots shorter than 3 seconds unless the user explicitly requests an accent cut or fast rhythm.
- Do not give every shot the same duration, lens, framing, or motion.
- Let grandeur breathe: hold after the reveal instead of cutting immediately.
- Make shot durations sum exactly to the requested total.

## Motion rules

- Use one primary move per shot: slow push, pullback reveal, lateral parallax, crane rise/fall, restrained orbit, tilt reveal, tracking follow, or locked-off tableau.
- Keep architecture stable. Move camera, cloth, mist, foliage, water, birds, or light—not the building's geometry.
- Specify speed and direction. Replace `镜头运动` with concrete instructions such as `camera slowly dollies forward by a small distance`.
- Keep movement extent consistent with the framing change. Large subject-size changes require a correspondingly large pullback, crane move, lens change, or cut; do not claim a tiny move produces an extreme-wide transformation.
- Start from a stable composition and end on another stable composition.
- Avoid simultaneous fast pan, zoom, orbit, roll, crane, and subject action.
- Prohibit random morphing, boiling ornament, sliding columns, duplicated people, and changing building silhouettes.

## Continuity rules

- Lock adult character identity, count, outfit colors, hairstyle silhouette, and carried objects.
- Lock the main landmark silhouette, roof count, gate shape, bridge direction, and location relative to the character.
- Lock sun/moon direction, shadow direction, palette, material family, weather state, and horizon orientation.
- Permit only motivated evolution: clouds open, rain stops, light strengthens, garment becomes wetter, or the character changes position.
- Repeat the minimum continuity invariants inside every shot prompt; do not rely on a global note alone.

## Direct-generation routing

- Generate or use anchor images before video when character, landmark, or architecture consistency matters.
- Label every input by role: identity anchor, landmark anchor, first frame, last frame, style reference, or motion reference.
- If the user names a platform, load its current video-generation Skill or tool guidance before applying provider-specific limits or syntax. Do not hardcode changing model capabilities here.
- Do not create extra variants, spend credits, or submit jobs beyond the user's explicit request.
- Return generated media by default when direct generation is requested; keep internal planning concise.

## Standard output

Unless the user requests another mode, return:

1. `参数锁定`
2. `一句话故事脊柱`
3. `连续性锁定卡`
4. `分镜总表`: shot number, time range, duration, function, framing/lens, camera movement, and end state
5. `逐镜头提示词`: one copy-ready fenced `text` block per shot
6. `全局负面约束`: separate fenced `text` block
7. `生成顺序`: anchor/keyframe and shot-generation order when useful

For `只要分镜`, omit full prompts. For `只要提示词`, keep a compact parameter header, then output per-shot prompts and global negative constraints. For diagnosis, lead with evidence, then provide the corrected shot table and only the prompts needed to demonstrate the fix.

## Per-shot prompt requirements

Every shot prompt must include:

- exact duration and ratio
- shot function and initial composition
- subject action with a clear gaze or travel target
- one lens/framing choice
- one primary camera movement with speed and direction
- restrained environmental motion
- explicit end state or last-frame composition
- cross-shot continuity invariants
- shot-specific avoid items

Keep private reasoning internal. Expose decisions, locks, and visible effects—not hidden chain-of-thought.
