# 东方仙侠运镜导演

`xianxia-cinematic-video-director` 是一个面向 Codex / Agent Skills 体系的东方仙侠电影视频导演 Skill。它将场景构想、图片提示词、关键帧或参考视频，扩展为具有故事推进、空间连续性、明确运镜和稳定首尾状态的多镜头视频方案。

它关注的是时间、镜头功能、运动路径与跨镜头一致性，不会输出一组彼此无关的“漂亮仙侠画面”。

> Cinematic Eastern xianxia video direction for story spines, shot lists, camera choreography, continuity locks, keyframes and per-shot generation prompts.

## 核心能力

- 生成一句话故事脊柱、连续性锁定卡、分镜总表与逐镜头视频提示词。
- 为每个镜头指定初始画面、人物动作、单一主运镜、环境运动与稳定结束状态。
- 根据总时长自动规划镜头数量和节奏，并确保各镜头时长之和准确。
- 设计缓慢推近、后拉揭示、横向视差、升降、跟随、仰拍揭示、克制环绕与固定机位等运镜。
- 锁定人物、服装、建筑轮廓、地理关系、光线方向、风向、天气和色彩，减少跨镜头漂移。
- 诊断参考视频中的剪辑过快、镜头重复、运动混乱、建筑变形、人物复制、颜色漂移和空间断裂。
- 支持首帧/尾帧规划、图生视频提示词，以及在明确授权后的直接视频生成工作流。
- 支持 `16:9`、`21:9`、`4:3`、`3:2`、`4:5`、`9:16`。

## 默认参数

未明确指定时使用：

- 画幅比例：`16:9`
- 总时长：`30秒`
- 镜头数量：`6`
- 节奏：`庄严舒缓`
- 空间尺度强度：`史诗级`
- 饱和策略：`选择性高饱和`

默认30秒结构会用较少但可读的镜头逐步完成世界揭示、人物定位、空间行进、尺度升级、情绪停顿和最终抵达，而不是快速蒙太奇。

## 导演原则

### 一条故事脊柱

每个视频先明确从开始到结束发生了什么，例如：

```text
等待 -> 察觉 -> 相遇 -> 同行 -> 仰望 -> 抵达
```

### 一个镜头只承担一个主要功能

- 揭示世界
- 建立人物尺度
- 说明行进路径
- 升级建筑或自然尺度
- 完成情绪节点
- 展示最终目的地

### 一个镜头只使用一个主运镜

避免在同一镜头中同时快速平移、推拉、环绕、升降、旋转和变焦。建筑保持稳定，运动主要来自摄像机、人物、衣料、云、水、树叶、鸟群与光线。

### 首尾都必须稳定

每条逐镜头提示词都定义：

1. 稳定的初始构图
2. 一个清晰人物动作链
3. 一个有方向、速度和幅度的主运镜
4. 一至两层克制环境运动
5. 稳定的结束画面及新增信息

## 安装

### Windows PowerShell

```powershell
git clone https://github.com/liyue-aigc/xianxia-cinematic-video-director.git
Copy-Item -Recurse -Force `
  .\xianxia-cinematic-video-director\xianxia-cinematic-video-director `
  "$env:USERPROFILE\.codex\skills\xianxia-cinematic-video-director"
```

如果目标目录已经存在，请先自行备份。重新启动 Codex 或刷新 Skill 列表后即可调用。

### macOS / Linux

```bash
git clone https://github.com/liyue-aigc/xianxia-cinematic-video-director.git
mkdir -p ~/.codex/skills
cp -R ./xianxia-cinematic-video-director/xianxia-cinematic-video-director ~/.codex/skills/
```

## 最小调用示例

```text
使用 $xianxia-cinematic-video-director。

核心故事：一名旅人在崖畔等待同伴，最终二人共同走向云海尽头的天宫。

请输出标准完整格式。
```

## 完整调用示例

```text
使用 $xianxia-cinematic-video-director。

总时长：30秒
画幅比例：21:9
镜头数量：6
节奏：庄严舒缓
核心故事：等待 -> 发现 -> 同行 -> 抵达
起点：崖畔古松下的开放石台
路径：横跨云海的悬空长桥
终点：压出画面顶部的巨型天门
人物：两名虚构成年旅人，月白与孔雀青结构化仙衣，背影为主
空间尺度强度：超宏大
饱和策略：选择性高饱和
光线：清晨右侧低角度侧逆光
镜头偏好：缓慢横移揭示、稳定跟随、低机位仰拍、最终远景停留

输出参数锁定、故事脊柱、连续性锁定卡、分镜总表、逐镜头提示词、全局负面约束和生成顺序。
```

## 标准输出

1. 参数锁定
2. 一句话故事脊柱
3. 连续性锁定卡
4. 分镜总表
5. 逐镜头提示词
6. 全局负面约束
7. 推荐生成顺序

分镜总表会记录镜头编号、时间范围、时长、功能、景别/焦段、主运镜和结束状态。逐镜头提示词会重复必要的连续性约束，避免只依赖一段容易被模型忽略的全局说明。

## 连续性锁定内容

- 人物数量、成年身份、身形、发型轮廓、服装颜色和随身物品
- 主建筑轮廓、屋檐层数、门洞形状、桥梁方向与可裁切部分
- 起点、路径、终点、地平线和人物行进方向
- 太阳或月亮方向、阴影方向、风向、云层移动和天气变化
- 主色、近中性色、最高纯度强调色和材质体系
- 湿润、破损、开门、持物和人物位置等跨镜头状态

## 目录结构

```text
xianxia-cinematic-video-director/
├── README.md
└── xianxia-cinematic-video-director/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── continuity-and-motion.md
        ├── prompt-patterns.md
        ├── shot-grammar.md
        └── visual-baseline.md
```

## 与视觉导演配合

视频的单张视觉设定、建筑关键帧或严格首帧可以配合 [xianxia-visual-director](https://github.com/liyue-aigc/xianxia-visual-director) 生成。本 Skill 仍可独立工作，不强制依赖图片 Skill。

两套 Skill 同时使用时，建议按以下顺序：

1. 使用视觉导演锁定世界、建筑、人物、服装、画幅、色彩与光线。
2. 选择一至数张图片作为人物、地标、首帧或风格锚点，并明确每张图的角色。
3. 使用运镜导演建立故事脊柱、空间地图和连续性锁定卡。
4. 生成分镜与逐镜头视频提示词。
5. 先验证关键镜头，再按故事顺序生成其余镜头。

## 注意事项

- Skill 不绑定特定视频模型；只有用户明确指定平台时，才应读取该平台的当前能力与参数限制。
- 分镜或参数请求不等于授权直接生成可能产生费用的视频。
- 为保证稳定性，优先使用少而清晰的动作和运镜，不让建筑变形来制造运动。
- 参考图片应明确标记为人物身份锚点、服装锚点、地标锚点、风格参考、严格首帧、严格尾帧或运动参考。

## License

本仓库暂未附带开源许可证。仓库公开可见不等于授予复制、修改或再分发许可。
