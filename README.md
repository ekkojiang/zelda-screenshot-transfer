# zelda-screenshot-transfer

一个用于 Codex 的图片转绘 Skill：根据现实参考照片，生成 Nintendo Switch《塞尔达传说：王国之泪》实机截图质感的转绘提示词，也可以配合图片生成工具进行转绘测试。

当前重点是 **MAXIMUM TOTK IN-GAME RENDERING FIDELITY**：尽量贴近《王国之泪》Switch 实机 gameplay footage 的 clean digital cel-shading 游戏引擎渲染，而不是插画、绘画、电影 CG 或写实摄影。

当前版本：`v0.2.1`

## 作者主页

- 小红书主页：[https://www.xiaohongshu.com/user/profile/59a4ee346a6a6972f6a7aec4](https://www.xiaohongshu.com/user/profile/59a4ee346a6a6972f6a7aec4)

## 版本迭代

### v0.2.1 - 安装说明补充

- 在 README 顶部补充当前版本号
- 在安装方法中新增一句话 Codex 安装命令，方便直接复制到 Codex 对话中使用

### v0.2.0 - TOTK 实机渲染保真强化

- 将核心目标升级为 `Nintendo Switch Tears of the Kingdom gameplay screenshot - MAXIMUM TOTK IN-GAME RENDERING FIDELITY`
- 新增开头 + 结尾的包围式渲染约束，防止画面跑向插画、绘画、电影 CG、HDR 或写实摄影
- 新增必填渲染模块：`LIGHTING`、`SHADOW AND SHADING`、`COLOR PALETTE`、`MATERIALS`
- 要求为 3-5 个主要元素写出 `base → mid-tone → shadow` 色阶公式，强化 3-4 级柔和 cel-shaded 阴影
- 强化大色块、低频材质、低对比明亮光照、简化粒子、干净数字 3D 游戏引擎质感
- 新增常见问题修复：太像插画、阴影太复杂、过度 HDR/电影感、UI 或文字太抢戏
- 保留现实参考图结构优先、中文区域发现 UI、林克单人默认、现代元素海拉鲁化转译等原有工作流

### v0.1.0 - 初始照片转绘工作流

- 支持根据现实照片生成 BOTW/TOTK 风格转绘提示词
- 支持 9:16 手机竖屏、林克单人、轻量 HUD、区域发现 UI、中文按键动词
- 支持根据场景选择奔跑、攀爬、滑翔、盾滑、烹饪、休憩、睡觉、潜行等玩法时刻

## 免责声明

本项目是非官方、粉丝向、非商业用途的 Codex Skill，仅用于个人学习、研究和工作流测试。

本项目与 Nintendo、The Legend of Zelda、Breath of the Wild、Tears of the Kingdom 及相关权利方没有任何隶属、赞助、认可或授权关系。

所有商标、游戏名称、角色、视觉参考和相关知识产权均归各自权利方所有。请勿将本项目、提示词或生成结果用于售卖、广告、周边、付费服务，或任何可能让人误认为官方授权的场景。

使用者需要自行确认自己的使用方式符合版权、商标、平台规则和当地法律要求。本说明不构成法律建议。

## 这个 Skill 能做什么

- 根据现实照片生成塞尔达风格转绘提示词
- 把城堡、山谷、村庄、森林、湖泊、沙漠、营地等照片转成开放世界游戏截图感
- 根据参考图内容自动设计玩法时刻，例如奔跑、攀爬、滑翔、烹饪、休憩、睡觉、潜行
- 默认使用 `TOTK 王国之泪默认造型，林克单人`
- 默认输出 `9:16` 手机竖屏构图
- 自动加入轻量 HUD、区域发现 UI、中文按键动词
- 使用元素级色阶公式控制 TOTK 实机 cel-shaded 渲染
- 强制大色块、低频材质、3-4 级柔和阴影、低对比明亮光照
- 在生成图片时，同时输出可复用的生图提示词

## 安装方法

一句话让 Codex 安装：

```text
请安装这个 Codex Skill：https://github.com/ekkojiang/zelda-screenshot-transfer
```

把整个 skill 文件夹放到 Codex 的 skills 目录下：

```text
~/.codex/skills/zelda-screenshot-transfer/
```

目录结构应类似：

```text
zelda-screenshot-transfer/
  SKILL.md
  agents/
    openai.yaml
```

如果你是从这个仓库复制，可以把仓库里的文件夹复制到：

```text
/Users/你的用户名/.codex/skills/zelda-screenshot-transfer/
```

## 使用方法

在 Codex 对话里上传一张参考图，然后直接说：

```text
使用 zelda-screenshot-transfer 转绘这张图
```

或者：

```text
[$zelda-screenshot-transfer] 使用这张图转绘，并输出提示词
```

如果只想要提示词，不生成图片：

```text
使用 zelda-screenshot-transfer 根据这张参考图生成提示词
```

## 输出提示词结构

Skill 会按下面结构生成提示词。新版更重视渲染可控性，不再只用一两句“画风描述”，而是用多个固定模块锁定 TOTK 实机截图质感：

```text
Nintendo Switch Tears of the Kingdom gameplay screenshot - MAXIMUM TOTK IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual TOTK Switch gameplay footage, NOT illustration, NOT anime art, NOT painting.

RENDERING STYLE - TOTK SWITCH IN-GAME (CRITICAL):
LARGE FLAT UNIFIED COLOR BLOCKS dominate every surface; CLEAN DIGITAL CEL-SHADING like 3D game engine rendering; 3-4 level soft gradient shadows ONLY; LOW-FREQUENCY hand-painted game textures; NO fine brush strokes, NO painting texture, NO illustration style.

SCENE：保留参考图核心构图、主体、地形、道路/水面/建筑/天空等识别特征；现代设施和游客做海拉鲁化转译或移除；画面尺寸比例：9:16，1440x2560
CHARACTER AND GAMEPLAY：TOTK 王国之泪默认造型，林克单人；根据参考图选择一个明确游戏动作，并说明是否显示耐力轮
ZELDA ELEMENTS：3-7 个场景适配元素，只列名称
UI：按需加入区域发现/相机/轻量 HUD；所有可读 UI 使用中文；真实招牌和广告转为不可读海拉鲁纹样

LIGHTING - TOTK GAME ENGINE STYLE:
Soft LOW-CONTRAST lighting, NOT dramatic, NOT cinematic; gentle 3-level shadows; Overall BRIGHT and clearly visible; NO HDR, NO photorealistic lighting.

SHADOW AND SHADING - TOTK SPECIFIC:
为 3-5 个主要元素写出 base color → mid-tone → shadow color 色阶公式，限制为 3 tones ONLY。

COLOR PALETTE - TOTK 场景类型:
为主要元素列出 2-4 个颜色层级，默认 3 tones max；所有颜色 clean, bright, slightly desaturated。

MATERIALS - LARGE FLAT COLOR BLOCKS:
主要材质必须是 unified flat color areas / LARGE FLAT COLOR BLOCKS，并明确 NO texture complexity, NO fine surface detail。

FINAL EMPHASIS - MUST LOOK LIKE ACTUAL TOTK SWITCH GAMEPLAY:
Every surface is LARGE FLAT COLOR BLOCK. Shadows are SIMPLE 3-4 tone gradients. Lighting is SOFT, LOW-CONTRAST, even. CLEAN DIGITAL 3D GAME RENDERING. NOT illustration, NOT anime, NOT painting style.
```

## 核心渲染控制

当前版本最重要的是这组开场声明，适合每次转绘都放在提示词最前面：

```text
Nintendo Switch Tears of the Kingdom gameplay screenshot - MAXIMUM TOTK IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual TOTK Switch gameplay footage, NOT illustration, NOT anime art, NOT painting.
```

如果生成结果还是太像插画或写实，可以用下面方向二次迭代：

```text
NO fine brush strokes, NO painting texture, NO illustration style.
CLEAN DIGITAL 3D GAME RENDERING.
Every surface is LARGE FLAT COLOR BLOCK.
Shadows are SIMPLE 3-4 tone gradients.
NO texture complexity, NO fine surface detail.
```

## 工作流说明

1. 分析参考图  
   识别画面主体、构图、镜头机位、天气、光线、前景/中景/远景，以及需要保留的建筑、道路、山体、树林、水面或营地结构。

2. 保留原图识别度  
   不把照片完全改成另一个场景，而是在保留核心结构的基础上进行海拉鲁化转译。

3. 选择玩法时刻  
   根据画面内容自动选择动作：

   - 道路、村道、桥梁：奔跑、步行、对话
   - 城堡、塔楼、岩壁：攀爬、靠近、观察
   - 高山、云海、峡谷：滑翔、俯冲、远眺
   - 雪坡、沙丘、长下坡：盾滑
   - 帐篷、篝火、夜间营地：休憩、烹饪、睡觉、仰望天空
   - 水边、湖泊、海岸：游泳、木筏、观察隐藏宝箱
   - 怪物营地、废墟、窄巷：潜行、战斗、观察巡逻

4. 转成游戏实况截图感  
   目标不是写实摄影，也不是电影 CG，而是明亮、清爽、低频材质、大色块、柔和光影、轻空气透视的 Switch 实机截图感。

   实机截图校准重点：

   - 日间场景：浅青蓝天空、薄雾远景、亮绿色草地、柔和暖色阳光
   - 黄昏场景：金色空气雾、暖边缘光、发白高光，不做 HDR 电影感
   - 森林/魔法场景：蓝绿色环境雾、柔软轮廓、低对比阴影
   - 天空岛/神庙/龙影场景：青白色空气透视、柔和发光、远景大幅降细节
   - 角色和可交互物体：轮廓清楚、色块干净、不要写实皮肤/布料/金属纹理

5. 加入适量塞尔达元素  
   按场景选择元素，例如料理锅、原版宝箱、旅行商人、波克布林巡逻、左纳乌神庙、鸟望台、飞行魔物等。不要把所有元素硬塞进同一张图。

6. 输出图片和提示词  
   如果用户要求生成图，先生成图片，再附上本次使用的结构化提示词，方便继续迭代。

## 设计重点

- 参考图优先，保持原图构图和主体辨识度
- 默认林克单人，除非用户明确要求塞尔达或其他角色
- 玩法时刻要像真实游戏行为，不要总是站在画面中央摆拍
- UI 要像游戏截图的一部分，不要像海报标题
- 区域发现 UI 要中文、轻量、淡色发光、无矩形底纹
- 草地、树叶、石头、屋顶、水面都减少真实纹理和细碎笔触
- 避免 HDR、PBR、真实摄影、湿润反光、硬黑阴影

## 示例请求

```text
使用 zelda-screenshot-transfer 转绘这张夜晚森林露营图，在夜空中加入荒野之息风格的发光龙影，并输出提示词。
```

```text
使用 zelda-screenshot-transfer 根据这张古堡照片生成 9:16 手机竖屏塞尔达实况截图风格提示词。
```

```text
使用 zelda-screenshot-transfer 转绘这张雪山村庄图，林克可以在雪坡上盾滑，输出图片和提示词。
```

## 文件说明

```text
skills/zelda-screenshot-transfer/SKILL.md
```

Skill 的核心工作流和提示词规则。

```text
skills/zelda-screenshot-transfer/agents/openai.yaml
```

Codex 中显示 skill 名称、简介和默认调用语句的配置文件。
