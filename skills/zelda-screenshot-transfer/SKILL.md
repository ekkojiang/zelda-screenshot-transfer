---
name: zelda-screenshot-transfer
description: "Transform real-world reference photos into Nintendo Switch The Legend of Zelda: Tears of the Kingdom in-game screenshot prompts or generated images with maximum TOTK in-game rendering fidelity. Use when the user provides landscape, town, castle, mountain, street, village, ruin, desert, lake, forest, travel, coast, shrine, architecture, or real-place photos and asks for Zelda/BOTW/TOTK screenshot transfer, photo-to-gameplay prompt writing, image-to-image prompts, 9:16 mobile covers, Link as the single player character, dynamic gameplay moments, Chinese TOTK-style UI, area discovery banners, HUD, stamina ring, Zonai shrines, treasure chests, enemies, NPC conversion, or reusable real-photo-to-TOTK workflows."
---

# 塞尔达实况转绘

Convert real-world reference photos into **Nintendo Switch Tears of the Kingdom gameplay screenshots**. The priority is **MAXIMUM TOTK IN-GAME RENDERING FIDELITY**: clean digital 3D cel-shaded game-engine output, not illustration, anime art, painting, poster art, cinematic CG, or photorealism.

This is a fan-made, non-commercial workflow for personal learning, research, and prompt testing only. It is not affiliated with, endorsed by, sponsored by, or approved by Nintendo, The Legend of Zelda, Breath of the Wild, Tears of the Kingdom, or any related rights holders. Do not use outputs for commercial sale, advertising, merchandising, paid services, or uses that imply official authorization.

## Output Mode

- If the user asks for prompts, return the final prompt in one code block unless they ask for explanation.
- If the user asks to generate images, use the available image generation workflow. Prefer `generate_image_gpt_image_2` when available.
- If generating from a reference photo, generate first, then provide the final prompt unless the user asks for image only.
- If both prompt and image are requested, generate first, then provide the prompt.
- Use Chinese for user-facing final prompts, but keep the English rendering-control blocks exactly because they strongly steer image models.

## Reference Analysis

Before writing the prompt, identify only what affects transfer:

- Core subject: coast, town, castle, street, mountain, lake, desert, village, ruins, forest, interior, etc.
- Recognizable features to preserve: skyline, building silhouette, terrain shape, water path, road, bridge, cliff, stair, cloud pattern, tree line, harbor, horizon.
- Scene type: exploration, combat, rest, interaction, cooking, sleep, travel, stealth, climbing, gliding, shield-surfing.
- Environment: time, weather, place confidence, season, visibility.
- Best gameplay action from the scene and camera.
- UI needs: area discovery banner, normal HUD, camera UI, stamina ring, status effect, or no UI.
- Modern people, vehicles, signs, roads, barriers, and facilities that must be removed or converted.

Preserve the reference photo's identity. Improve it into a playable TOTK moment, not a poster.

## Planning Workflow

Before filling the final prompt, decide:

1. 场景类型：探索 / 战斗 / 休息 / 互动 / 料理 / 睡觉 / 潜行 / 旅行
2. 环境设定：时间 / 天气 / 地点 / 季节 / 真实地名可信度
3. 角色动作和游戏机制：奔跑 / 攀爬 / 滑翔 / 盾滑 / 潜行 / 对话 / 烹饪 / 睡觉等
4. UI 需求：发现横幅 / 相机 / 体力轮 / 状态效果 / 轻量 HUD / 无 UI
5. 构图和视角：远景 / 高机位 / 低机位 / 第三人称跟随 / 近景互动

Do not output this planning checklist unless the user asks. Reflect the decisions in the final prompt.

## Prompt Template

When a reference image is provided, always derive concrete content from the image. Never output placeholders such as `[元素1]`, `[参考图核心结构]`, `[真实地名]`, or `[3-5 个关键词]`.

Use this order for prompt-only output and image-generation prompts:

```text
Nintendo Switch Tears of the Kingdom gameplay screenshot - MAXIMUM TOTK IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual TOTK Switch gameplay footage, NOT illustration, NOT anime art, NOT painting.

RENDERING STYLE - TOTK SWITCH IN-GAME (CRITICAL):
LARGE FLAT UNIFIED COLOR BLOCKS dominate every surface; CLEAN DIGITAL CEL-SHADING like 3D game engine rendering; 3-4 level soft gradient shadows ONLY (base → mid-tone → shadow); LOW-FREQUENCY hand-painted game textures, each area ONE solid color; NO fine brush strokes, NO painting texture, NO illustration style; SHARP clean edges between color zones; DIGITAL 3D GAME AESTHETIC, minimal surface detail.

SCENE：保留<参考图核心构图、主体、地形、道路/水面/建筑/天空等识别特征>；现代设施和游客做海拉鲁化转译或移除；画面尺寸比例：9:16，1440x2560
CHARACTER AND GAMEPLAY：TOTK 王国之泪默认造型，林克单人；<一句话写清动作>，<正在消耗体力，显示耐力轮 / 不消耗体力，不显示耐力轮>
ZELDA ELEMENTS：<3-7 个场景适配元素，只列名称>
UI：<按需加入区域发现/相机/轻量 HUD>；所有可读 UI 使用中文，按键动词只用中文；场景内真实招牌和广告转为不可读海拉鲁纹样或 1-3 字中文

LIGHTING - TOTK GAME ENGINE STYLE:
Soft LOW-CONTRAST lighting, NOT dramatic, NOT cinematic; gentle 3-level shadows: base color → mid-tone → shadow tone; warm rim lighting on character edges; blue-green atmospheric perspective for distant elements; simple flat illumination with subtle directional hints; Overall BRIGHT and clearly visible; NO HDR, NO photorealistic lighting, NO complex light rays.

SHADOW AND SHADING - TOTK SPECIFIC:
All shadows are SOFT 3-4 level gradients ONLY; NO hard shadow edges, NO complex shadow shapes; shadows are simple darker tones of base color; ambient occlusion only as gentle corner darkening; NO dramatic contrast, everything visible and clear.
<主要元素1> shading: <base color> → <mid-tone> → <shadow color> (3 tones ONLY)
<主要元素2> shading: <base color> → <mid-tone> → <shadow color> (3 tones ONLY)
<主要元素3> shading: <base color> → <mid-tone> → <shadow color> (3 tones ONLY)
<主要元素4> shading: <base color> → <mid-tone> → <shadow color> (3 tones ONLY)

COLOR PALETTE - TOTK <场景类型>:
<元素1>: Flat <base color>, <mid-tone>, <shadow tone> (3 tones max)
<元素2>: LARGE FLAT <color> BLOCKS with minimal variation
<元素3>: <color> base → <color> mid → <color> shadow
Sky/gradients: 2-3 tones maximum, soft transitions; all colors CLEAN, BRIGHT, slightly desaturated; low contrast between light and shadow areas.

MATERIALS - LARGE FLAT COLOR BLOCKS:
<材质1>: rendered as unified flat color areas with soft 2-3 tone shading, NO texture complexity, NO fine surface detail
<材质2>: LARGE FLAT <color> BLOCKS, simplified surface, clean edges, NO texture complexity, NO fine surface detail
<材质3>: simple <color> base with gentle <color> shadows, clean smooth surfaces with minimal variation

PARTICLE EFFECTS - TOTK STYLE:
<仅在有雪/雨/火/雾/蒸汽/魔法/神庙光效时填写；LOW-OPACITY flat shapes, simple geometric forms, clean digital particle effect style, NOT realistic volumetric, NO complex particle systems>

FINAL EMPHASIS - MUST LOOK LIKE ACTUAL TOTK SWITCH GAMEPLAY:
Every surface is LARGE FLAT COLOR BLOCK. Shadows are SIMPLE 3-4 tone gradients. Lighting is SOFT, LOW-CONTRAST, even. NO fine detail, NO texture complexity. CLEAN DIGITAL 3D GAME RENDERING. Simplified forms and unified colors. TOTK Switch in-game screenshot aesthetic. NOT illustration, NOT anime, NOT painting style.
```

Delete the `PARTICLE EFFECTS` block when no particles or special effects apply.

## Required Prompt Fields

Every final prompt must include:

- Scene description: concrete character, action, environment, composition, and preserved reference features.
- `SHADOW AND SHADING`: 3-5 main elements with explicit color-step formulas.
- `COLOR PALETTE`: main elements with 2-4 tones, usually 3 tones max.
- `MATERIALS`: main materials rendered as large flat color blocks.
- Opening and final emphasis blocks, unchanged in meaning.

Optional:

- `PARTICLE EFFECTS`: include only for snow, rain, fire, steam, fog, magic, shrine glow, dust, or similar effects.
- Special light source: if torch, moonlight, magic light, shrine glow, or firelight exists, add one short clause inside `LIGHTING`.

## Style Anchor Rules

Start every image prompt with these two lines:

```text
Nintendo Switch Tears of the Kingdom gameplay screenshot - MAXIMUM TOTK IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual TOTK Switch gameplay footage, NOT illustration, NOT anime art, NOT painting.
```

Then include `RENDERING STYLE - TOTK SWITCH IN-GAME (CRITICAL)` before scene content. End every prompt with `FINAL EMPHASIS - MUST LOOK LIKE ACTUAL TOTK SWITCH GAMEPLAY`.

Do not scatter extra style essays across the prompt. Rendering control lives in the opening, lighting, shading, color, materials, particles, and final emphasis blocks.

## TOTK Rendering Calibration

Use the user's BOTW/TOTK screenshots as visual target when supplied. Otherwise default to TOTK Switch gameplay:

- Bright, saturated, soft, low-contrast, clearly playable, and game-rendered.
- Clean daylight: cyan-blue sky, warm sunlit color planes, vivid mint greens, golden yellows, turquoise blues, soft highlight bands.
- Large flat unified color blocks on every surface.
- Clean digital cel-shading with 3-4 level soft gradients only.
- Low-frequency hand-painted **game texture maps**, not painterly brush texture.
- Grass appears as bright color masses with only a few readable blades near camera.
- Trees and leaves appear as clustered stylized volumes, not individually detailed leaves.
- Rocks, roofs, walls, roads, floors, cliffs, and water use low-frequency blocks, not scratches, pores, asphalt grain, or tiny brush marks.
- Distant mountains, buildings, trees, and sea horizon are lighter, bluer, softer, and lower contrast.
- Character and interactable props have clear game silhouettes and smooth shaded color planes.

Avoid:

- Illustration, anime art, painting, concept art, poster key art.
- Movie CG, cinematic trailer lighting, photorealistic rendering, HDR, complex light rays, volumetric realism.
- Fine brush strokes, fragmented painterly texture, scratchy texture, noisy foliage.
- Glossy wet stone, hard black shadows, realistic road asphalt, detailed leaf/grass microtexture.
- Mobile-app-looking UI, giant travel titles, readable tourism signs as visual focus.

## Character Rules

- Default: `TOTK 王国之泪默认造型，林克单人`.
- If the user explicitly asks for BOTW, use `BOTW 旷野之息默认造型，林克单人`.
- If the user asks for Zelda or companions, follow that request. Otherwise do not add Zelda, companions, duplicate Link, or unrelated heroes.
- Do not describe Link's clothing, hair, shield, sword, face, or gear in detail. The game/version anchor handles the default look.
- If the reference photo contains modern pedestrians, tourists, seated people, workers, cars, signs, or barriers, convert those reference-photo items into Zelda-world equivalents or remove them. This rule must not replace Link.

NPC conversion examples:

- Tourists -> 海利亚村民 / 旅行商人 / 驿站旅人 / 希卡族研究员
- Staff -> 巡逻守卫 / 研究员 / 驿站老板
- Plastic signs / railings -> 木牌 / 石碑 / 古代机关 / 栅栏
- Vehicles / modern facilities -> 马车 / 木筏 / 驿站 / 机关平台

Avoid modern clothing, realistic tourists, uniforms, cars, phones, logos, and readable real-world signs.

## Gameplay Moment Rules

Choose Link's action from the reference content and camera angle. Write one clear gameplay sentence with stamina behavior.

- Roads, village paths, bridges, town streets -> walking, running, talking, observing, riding.
- Cliffs, castle walls, towers, ruins, steep rocks -> climbing or preparing to climb.
- High overlooks, valleys, cloud seas, mountains, rooftops -> gliding or preparing to glide.
- Snow slopes, sand dunes, long downhill paths -> shield-surfing.
- Campsites, campfires, tents, inns, warm night scenes -> resting, cooking, sleeping, watching the sky.
- Water, rivers, lakes, coasts -> swimming, rafting, standing on shore, watching a hidden chest.
- Meadows, animals, quiet scenic views -> walking, observing, riding, calm rest.
- Enemy camps, ruins with patrols, narrow alleys -> sneaking, fighting, observing from cover.

Use `正在消耗体力，显示耐力轮` for climbing, gliding, swimming, sprinting, or other stamina actions. Use `不消耗体力，不显示耐力轮` for walking, observing, talking, cooking, resting, sleeping, riding, or normal shield-surfing unless requested otherwise.

Do not default to Link standing centered in the foreground. The action should make the reference photo feel playable.

## Zelda Elements

Choose 3-7 scene-appropriate names only. Do not explain appearance, material, or exact placement unless the user asks.

- Exploration: `TOTK 左纳乌神庙`, `原版神庙`, `鸟望台`, `高塔`, `天空遗迹`, `古代石门`, `山洞入口`, `传送台`, `女神像`
- Props: `原版宝箱`, `料理锅`, `篝火`, `木桶`, `矿石`, `武器架`, `木筏`, `滑翔伞`, `马匹`, `风扇`, `火箭`, `热气球`, `左纳乌装置`
- Enemies: `波克布林`, `蜥蜴怪`, `莫力布林`, `人马`, `丘丘`, `骷髅怪`, `岩石巨人`, `方块魔像`, `飞行魔物`
- NPCs: `海利亚村民`, `旅行商人`, `驿站老板`, `希卡族研究员`, `巡逻守卫`
- Environment gameplay: `敌人营地`, `巡逻路线`, `可攀爬岩壁`, `湖中隐藏宝箱`, `破碎吊桥`, `解谜石碑`, `机关门`

Fit elements to the photo:

- Water / coast / harbor / cliffs -> `木筏`, `湖中隐藏宝箱`, `蜥蜴怪`, `TOTK 左纳乌神庙`
- Meadows / roads / villages -> `旅行商人`, `原版宝箱`, `波克布林营地`, `马匹`
- Ruins / castles / mountains -> `原版神庙`, `高塔`, `可攀爬岩壁`, `飞行魔物`
- Camps / stables / village edges -> `料理锅`; do not put a cooking pot randomly in a street, desert, or open meadow.

## Real Place Naming

Use the strongest available real-place name for readable area UI.

- If the user names a place or the reference clearly depicts a known landmark, use that true Chinese place name as the middle UI line, e.g. `阿苏山`, `班贝格`, `罗滕堡`, `科尔多瓦清真寺`.
- Use the true upper region as the bottom UI line when known, e.g. `日本·熊本`, `德国·巴伐利亚`, `法国·奥克西塔尼`.
- Do not replace a known place with a generic invented label in readable UI.
- If location confidence is low, use a neutral scene name without pretending it is a real place, or omit area discovery UI for image generation if text control is risky.
- `海拉鲁地图区块` may include a gameplay-flavored subtitle, but readable UI should stay true to the real place when known.

## UI Rules

- Add one subtle area discovery UI by default unless the user asks for no UI.
- Use the structure: `顶部「发现！」 / 中间「<真实地名或中性场景名>」 / 底部「<国家·城市/地区或上级区域>」`.
- Keep it subtle: main place name width <= 40% of image width, height <= 6%, fade-in small text, pale glow, no rectangle, no dark panel, do not occupy the sky.
- Do not use game-world names such as `海拉鲁`, `格鲁德高地`, `卡卡里科村`, or `海拉鲁城堡` for readable UI unless the user asks for a pure in-game Zelda location.
- All readable UI text must be Chinese.
- Button verbs must be Chinese only: `攻击`, `对话`, `调查`, `拾取`, `打开`, `攀爬`, `滑翔`, `跳跃`, `潜行`, `蓄力`, `瞄准`, `骑乘`, `丢出`, `烹饪`, `装备`, `休息`, `睡觉`.
- HUD should stay short and natural: `HUD：按 TOTK 原版游戏实况自然出现，不堆满`.
- Do not specify exact HUD position, count, or minimap geometry unless the user asks.
- Convert storefronts, banners, road signs, hotel names, and ads into unreadable Hyrule-like patterns, simple icons, or 1-3 character Chinese labels.

## Image Generation Parameters

When generating images, use:

- Tool: `generate_image_gpt_image_2` or the available image generation tool in the environment.
- Quality: `quality="high"` when supported.
- Size: `size="1440x2560"` for default 9:16 vertical mobile covers.
- Reference image: when a real scene reference is provided, pass it as `reference_image_urls` if the tool supports it.

If the user requests another size or aspect ratio, follow the user.

## Rendering Quality Checklist

Before delivering or iterating, verify:

- 大色块：每个表面是否为统一的平面色块，而不是细腻笔触？
- 阴影层级：阴影是否为 3-4 级柔和渐变，而不是复杂多层真实阴影？
- 光照对比：整体是否明亮、低对比、清楚可见，而不是戏剧性电影光？
- 边缘清晰：色块之间边缘是否清晰，而不是模糊绘画过渡？
- 粒子简化：粒子效果是否为低透明度简单几何形状，而不是真实体积效果？
- 材质简化：材质是否没有复杂纹理、微表面、照片颗粒和细节噪点？
- 整体风格：是否像数字 3D 游戏引擎截图，而不是插画/绘画/概念图？
- UI 准确性：UI 是否轻量、接近 TOTK 实况，所有可读文本是否为中文？
- 参考图识别：是否保留真实照片的核心构图、地点结构、道路/水面/建筑/地形关系？
- 色阶公式：是否为 3-5 个主要元素写了明确的 `base → mid → shadow`？

## Common Fixes

If the result fails the checklist, fix rendering drift by strengthening the rendering modules and element-level shading formulas. Do not add long cinematic, painterly, or photorealistic descriptions.

### Too illustrative or brushy

Symptoms: fine brush strokes, painterly texture, concept art feel, illustration style.

Fix:

- Strengthen both opening and final emphasis with `NO fine brush strokes, NO painting texture, NO illustration style`.
- Add `CLEAN DIGITAL 3D GAME RENDERING`.
- Add `DIGITAL 3D GAME AESTHETIC - minimal surface detail`.
- Add `NO texture complexity, NO fine surface detail` to every material line.

### Shadows are too complex

Symptoms: 5+ shadow bands, smooth realistic gradients, over-detailed occlusion, complex shadow shapes.

Fix:

- Rewrite each major element with: `<element> shading: <base> → <mid> → <shadow> (3 tones ONLY)`.
- Strengthen `3-4 level soft gradient shadows ONLY`.
- Strengthen `NO complex shadow shapes`.

### Too cinematic, HDR, or realistic

Symptoms: dramatic rim light, hard contrast, black shadows, volumetric beams, photorealistic road/stone/water.

Fix:

- Strengthen `Soft LOW-CONTRAST lighting, NOT dramatic, NOT cinematic`.
- Add `Overall BRIGHT and clearly visible`.
- Replace realism terms with `simple flat illumination`, `blue-green atmospheric perspective`, and `large flat color blocks`.

### Text or UI dominates

Symptoms: giant travel title, poster headline, English UI, garbled readable text, app-style overlays.

Fix:

- Keep area discovery UI small or remove it.
- Require all readable UI to be Chinese.
- Convert signs and ads into unreadable Hyrule-like patterns or 1-3 character Chinese labels.
- Keep `HUD：按 TOTK 原版游戏实况自然出现，不堆满`.

## Final Response

- For prompt-only requests, output only the final prompt code block.
- For image-generation requests, include a short note about what was generated and then include the concise generated prompt, unless the user explicitly asked for image only.
