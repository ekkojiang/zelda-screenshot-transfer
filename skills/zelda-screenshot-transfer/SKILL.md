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
3. 角色模式、动作和游戏机制：默认林克 / 用户参考原创角色 / 无角色；奔跑 / 攀爬 / 滑翔 / 盾滑 / 潜行 / 对话 / 烹饪 / 睡觉等
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
CHARACTER AND GAMEPLAY：<默认：TOTK 王国之泪默认造型，林克单人；或：基于人物参考图转译的原创海拉鲁冒险者，王国之泪实机角色效果，对标林克的比例、材质、装备复杂度和动作可信度>；<一句话写清动作>，<正在消耗体力，显示耐力轮 / 不消耗体力，不显示耐力轮>
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

STRICT SELF-CHECK TARGET:
The final image must pass: every surface uses LARGE FLAT COLOR BLOCKS; shadows are 3-4 tone soft gradients only; lighting is bright, low-contrast, and clearly readable; silhouettes are crisp game-engine shapes; particles are simplified; materials avoid PBR, photoreal texture, gritty noise, and microdetail; scene-specific microdetail is suppressed (leaves, stone cracks, window grids, fabric patterns, water ripples, city roads/cars/signage); UI is subtle Chinese gameplay UI only and never reads as a poster title; reference composition, landmark scale, camera angle, terrain/water/building relations, environmental density, and gameplay action are preserved; if an original character is used, it must read as a TOTK in-game playable Hyrule adventurer benchmarked against Link, not a modern photo person or fashion illustration.

FINAL EMPHASIS - MUST LOOK LIKE ACTUAL TOTK SWITCH GAMEPLAY:
Every surface is LARGE FLAT COLOR BLOCK. Shadows are SIMPLE 3-4 tone gradients. Lighting is SOFT, LOW-CONTRAST, even. NO fine detail, NO texture complexity. CLEAN DIGITAL 3D GAME RENDERING. Simplified forms and unified colors. TOTK Switch in-game screenshot aesthetic. NOT illustration, NOT anime, NOT painting style.
```

Delete the `PARTICLE EFFECTS` block when no particles or special effects apply.

## Required Prompt Fields

Every final prompt must include:

- Scene description: concrete character, action, environment, composition, and preserved reference features.
- Character mode: default Link, user-reference original character, or no character. If original, state that the figure is an original Hyrule adventurer with TOTK in-game rendering fidelity, benchmarked against Link's in-game proportion, material simplicity, gear readability, and gameplay action.
- `SHADOW AND SHADING`: 3-5 main elements with explicit color-step formulas.
- `COLOR PALETTE`: main elements with 2-4 tones, usually 3 tones max.
- `MATERIALS`: main materials rendered as large flat color blocks.
- `STRICT SELF-CHECK TARGET`: a compact pass/fail target that names large color blocks, 3-4 tone shadows, low-contrast lighting, simplified particles/materials, subtle Chinese UI, scene-specific microdetail suppression, and reference preservation.
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

Then include `RENDERING STYLE - TOTK SWITCH IN-GAME (CRITICAL)` before scene content. Include `STRICT SELF-CHECK TARGET` after particles/materials and before final emphasis. End every prompt with `FINAL EMPHASIS - MUST LOOK LIKE ACTUAL TOTK SWITCH GAMEPLAY`.

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

When the user supplies successful TOTK-like reference outputs, calibrate to the shared in-game traits rather than copying one scene literally:

- Camera: should feel playable and diegetic, with Link, traversal route, interactable object, enemy camp, NPC, or viewpoint logic visible. Avoid postcard composition even when the subject is a landmark.
- UI: use actual gameplay-style HUD as a realism anchor: hearts, status icons, minimap, stamina ring when relevant, action prompts, time/weather, and subtle Chinese discovery banner. UI must look like game state, not graphic design decoration.
- Lighting: bright clean daylight, soft bloom or haze only where game-like, low-to-medium contrast, clear visibility. Strong sunlight may appear through leaves, but avoid HDR glare, dramatic cinematic beams, or black crushed shadows.
- Vegetation: clustered stylized volumes, yellow-green and blue-green color masses, readable silhouette groups, sparse grass blades near camera only. Avoid individual photographic leaves, noisy shrubs, needle-like realism, or high-frequency grass carpets.
- Stone, cliffs, stairs, walls: low-frequency game texture maps with broad color planes. Keep some readable game detail, but avoid photorealistic cracks, pores, dirty stone grain, or architectural visualization detail.
- Snow, cloud, fog, haze: simplified soft game layers with blue atmospheric perspective. Avoid realistic volumetric cloud simulation, cinematic fog banks, or photographic mountain contrast.
- Water: clean teal/turquoise game surface with simplified reflection bands. Avoid glossy PBR reflections, realistic ripple microtexture, or dark photo water.
- Color: sky is clear cyan-blue; highlights are warm and slightly creamy; shadows lean blue-green; distant terrain fades lighter and bluer. The whole image should read as a Nintendo Switch gameplay capture.
- Text: all readable UI must be Chinese. Discovery title should be subtle and integrated; it must not become a giant poster headline.

For soft scene lighting, match the original TOTK in-game screenshot feel:

- Soft daylight is not a blur filter. It is clear sunlit visibility, warm cream highlights, pale cyan sky bounce, blue-green distance haze, and shadows that remain readable.
- Use soft bloom only around sun, bright sky, clouds, or discovery UI. Do not wash out interactable props, Link, stairs, cliff edges, roads, or enemies.
- In foreground and midground, keep silhouettes crisp while reducing material noise. In far distance, reduce contrast and saturation more aggressively.
- For cliffs and ruins, use chunky readable planes: warm beige rock face -> sage gray mid-tone -> blue-gray shadow. Keep cracks broad and sparse.
- For aerial terrain such as terraces, fields, water channels, roads, or switchback paths, treat the land as large clean pattern blocks. Contour lines and paths may be visible, but they must stay low-frequency and game-rendered.
- For high-altitude or cliff traversal shots, make Link's action and stamina UI clear; the gameplay action should anchor the view so the image does not become a landscape wallpaper.

## Scene-Specific Detail Suppression

Before generation, identify which reference features are likely to become too realistic or too decorative. Add the matching suppression lines directly inside `MATERIALS`, `STRICT SELF-CHECK TARGET`, or a narrow repair prompt.

- Trees, orchards, flower canopies, gardens: preserve canopy silhouette and fruit/flower placement, but suppress individual leaf texture, noisy twig networks, photographic leaf highlights, and high-frequency grass carpets. Use clustered stylized volumes and a few readable foreground shapes only.
- Stone walls, cliffs, ruins, old streets: preserve silhouette, block rhythm, stairs, cracks, and route logic, but suppress pebble texture, dirty pores, tiny cracks, gritty stone grain, and architectural visualization realism. Use broad sparse stone patches.
- Wood furniture, fabric, interiors, terraces: preserve object count and layout, but suppress wood grain microdetail, fabric pattern noise, cushion seams, table reflections, and decorative clutter. Use simple prop silhouettes and interaction prompts.
- Water, sea, lake, harbor: preserve horizon, boats, shore path, and water color, but suppress realistic ripple microtexture, glossy reflections, foam noise, and photographic sparkle. Use simplified color bands and soft reflection strips.
- Modern city skylines, glass towers, roads, parks: preserve landmark silhouette, building massing, bay/road/park relations, and camera height, but suppress dense window grids, mirror reflections, tiny cars, lane markings, construction detail, signage, and excessive gold ornament. Use broad facade panels and low-frequency civic-tower shapes.
- Snow, rain, fog, clouds: preserve weather density and mood, but suppress cinematic volumetric clouds, dramatic beams, hard contrast, and noisy particles. Use soft flat game layers.

If a scene has two competing risks, protect reference identity first, then suppress microdetail only in the risky material. Do not globally blur or empty the image.

Avoid:

- Illustration, anime art, painting, concept art, poster key art.
- Movie CG, cinematic trailer lighting, photorealistic rendering, HDR, complex light rays, volumetric realism.
- Fine brush strokes, fragmented painterly texture, scratchy texture, noisy foliage.
- Glossy wet stone, hard black shadows, realistic road asphalt, detailed leaf/grass microtexture.
- Mobile-app-looking UI, giant travel titles, readable tourism signs as visual focus.

## Character Rules

- Default: `TOTK 王国之泪默认造型，林克单人`.
- If the user explicitly asks for BOTW, use `BOTW 旷野之息默认造型，林克单人`.
- If the user provides a person reference or asks to replace Link with another visual identity, ask or suggest whether to use an original character when helpful. Use: `基于人物参考图转译的原创海拉鲁冒险者，王国之泪实机角色效果，对标林克`.
- Original character transfer must preserve only high-level design cues from the person reference: hairstyle silhouette, outfit color family, garment flow, approximate age impression, posture mood, and recognizable accessory rhythm. Do not copy modern background, power lines, logos, street signs, exact facial identity, or real-world fashion details literally.
- The original character must look like a playable TOTK-era in-game character, not a cosplay photo, fashion illustration, anime portrait, or photoreal person. Match Link as the quality benchmark: similar stylized body proportion, clean cel-shaded skin/hair/clothing, simplified hand-painted fabric, readable adventure gear, boots, belts, pouches, straps, and glider/weapon interaction when relevant.
- When replacing Link with an original character, keep the gameplay role that Link would normally perform: climbing, gliding, running, observing, talking, cooking, or resting. The character should be integrated into the same HUD/stamina/action logic as Link.
- Do not name the original character Link unless the user explicitly asks. Use neutral wording such as `原创海拉鲁冒险者`, `原创王国之泪风格角色`, or `原创可玩角色`.
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

Choose the player character's action from the reference content and camera angle. Use Link by default; if an original character replaces Link, choose the same kind of playable action and write one clear gameplay sentence with stamina behavior.

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
- Keep it subtle: main place name width <= 30% of image width, height <= 4%, fade-in small text, pale glow, no rectangle, no dark panel, do not occupy the sky or cover the primary landmark.
- For scenic, interior, rest, cooking, balcony, terrace, close-up, and small interaction scenes, prefer no discovery banner or a tiny translucent label only. Use a small button prompt near the interactable object (`调查`, `拾取`, `休息`, `烹饪`) as the main UI anchor.
- Discovery UI is allowed to be more visible only when the image is a true new-area reveal: high overlook, entering a town, reaching a landmark, gliding over a region, or first view of a large landscape. Even then, it must feel like in-game state, not a cover title.
- Do not use game-world names such as `海拉鲁`, `格鲁德高地`, `卡卡里科村`, or `海拉鲁城堡` for readable UI unless the user asks for a pure in-game Zelda location.
- All readable UI text must be Chinese.
- Button verbs must be Chinese only: `攻击`, `对话`, `调查`, `拾取`, `打开`, `攀爬`, `滑翔`, `跳跃`, `潜行`, `蓄力`, `瞄准`, `骑乘`, `丢出`, `烹饪`, `装备`, `休息`, `睡觉`.
- HUD should stay short and natural: `HUD：按 TOTK 原版游戏实况自然出现，不堆满`.
- Do not specify exact HUD position, count, or minimap geometry unless the user asks.
- Convert storefronts, banners, road signs, hotel names, and ads into unreadable Hyrule-like patterns, simple icons, or 1-3 character Chinese labels.
- If generated UI becomes the first thing the viewer notices, classify as at least `SOFT ISSUE`. If UI covers the landmark, gameplay action, route, character, or reference identity, classify as `HARD FAIL`.

## Image Generation Parameters

When generating images, use:

- Tool: `generate_image_gpt_image_2` or the available image generation tool in the environment.
- Quality: `quality="high"` when supported.
- Size: `size="1440x2560"` for default 9:16 vertical mobile covers.
- Reference image: when a real scene reference is provided, pass it as `reference_image_urls` if the tool supports it.

If the user requests another size or aspect ratio, follow the user.

## Rendering Quality Checklist

Before delivering or iterating, run this as a strict pass/fail check. If any required item fails, do not merely describe the issue; apply the matching fix module from `Common Fixes`, regenerate or rewrite the prompt, then check again.

- [ ] 大色块：每个表面是否为统一的平面色块？非细腻笔触。
- [ ] 阴影层级：阴影是否为 3-4 级柔和渐变？非复杂多层。
- [ ] 光照对比：整体是否明亮、低对比、清楚可见？非戏剧性。
- [ ] 边缘清晰：色块之间边缘是否清晰？非模糊绘画过渡。
- [ ] 粒子简化：粒子效果是否为低透明度简单几何形状？非真实体积。
- [ ] 材质简化：材质是否没有复杂纹理、微表面、照片颗粒和细节噪点？非写实质感。
- [ ] 场景微细节：是否按场景压制了叶片、石缝、窗格、反射、水纹、布纹、车流、道路标线等高频细节？
- [ ] 整体风格：是否像数字 3D 游戏引擎截图？非插画、绘画、概念图或海报。
- [ ] UI 准确性：UI 是否轻量、接近 TOTK 实况，所有可读文本是否为中文？发现标题是否小于画面宽度约 30%，且没有成为主视觉？
- [ ] 概念图风险：城市、神庙、城堡、天空岛或大型建筑是否没有跑成电影概念图、宣传海报、过度金色装饰或 Unreal/Octane 风格？
- [ ] 参考图识别：是否保留真实照片的核心构图、地点结构、道路/水面/建筑/地形关系？
- [ ] 原创角色：如果替换林克，角色是否是对标林克的王国之泪实机可玩角色？是否只保留人物参考的高层设计线索，且没有现代写真、街景、Logo、真实时装照质感？
- [ ] 色阶公式：是否为 3-5 个主要元素写了明确的 `base → mid → shadow (3 tones ONLY)`？

### Preservation-First Self-Check

Use this before deciding to regenerate. The goal is to keep the strongest first result when it already feels like playable TOTK footage. Do not over-optimize a good image into a cleaner but weaker poster.

Protect these successful traits:

- Reference composition: original camera angle, main subject scale, foreground/midground/background relation, and landmark silhouette.
- Gameplay anchor: Link or original character size, position, action, stamina/camera/action prompt, and whether the scene feels like a player is actually there.
- Weather and atmosphere: fog bands, snow density, rain streaks, haze, cloud layers, or soft light that sell the scene.
- Environmental density: city signs, forest trunks, village rooftops, terraces, snow poles, wires, roads, boats, or other identity-giving patterns.
- Readable game state: HUD, minimap, hearts, prompt, and discovery UI should support the screenshot without becoming graphic design.

Classify findings before repair:

- `PASS`: The image feels like TOTK gameplay, preserves the reference, and only has small imperfections. Deliver it. Do not regenerate.
- `SOFT ISSUE`: Minor title size, slight text artifacts, slightly busy particles, mildly dense leaves/stone/windows/water/fabric, or small material/detail issues, while composition and gameplay are strong. Prefer reporting the issue or making a very narrow prompt tweak. Do not change camera, player-character scale, route, weather, or scene density.
- `HARD FAIL`: The image becomes illustration/poster/photoreal CG, loses the reference structure, Link/action is missing or unnatural, UI dominates or covers the subject, modern objects remain as modern objects, materials are clearly high-frequency realistic, a city/landmark becomes a generic ornate fantasy concept image, or the first visual read is a poster title instead of playable game state. Regenerate with a targeted repair.

When a first generation is strong, preserve it. A second generation is only better if it keeps the same composition, action, weather character, and reference identity while fixing the specific failed item.

### Self-Check Repair Loop

Use this loop whenever an image has just been generated:

1. Inspect the image against every checklist item above and the `Preservation-First Self-Check`.
2. Classify the result as `PASS`, `SOFT ISSUE`, or `HARD FAIL`.
3. If `PASS`, deliver the image and briefly note why it passed. Do not regenerate.
4. If `SOFT ISSUE`, keep the image unless the user explicitly asked for another attempt. If you do regenerate, use a narrow repair prompt that preserves the exact camera, player-character scale, composition, weather, and scene density.
5. If `HARD FAIL`, name the failed items internally and map each failure to one or more `Common Fixes`.
6. Rewrite only the failed modules with stronger opening, material, shading, lighting, UI, or final emphasis controls. Avoid a full scene rewrite unless the reference structure was lost.
7. Regenerate once with the repaired prompt.
8. Compare first and second results. Choose the better image by gameplay believability and reference preservation, not by cleanliness alone. If the second result is cleaner but loses composition, scale, weather, or density, keep the first result and report the remaining soft issue.
9. If both results fail in the same way, report the remaining failure clearly and suggest the most targeted next repair.

## Common Fixes

If the result fails the checklist, fix rendering drift by strengthening the rendering modules and element-level shading formulas. Do not add long cinematic, painterly, or photorealistic descriptions.

### Too illustrative or brushy

Symptoms: fine brush strokes, painterly texture, concept art feel, illustration style.

Fix:

- Strengthen both opening and final emphasis with `NO fine brush strokes, NO painting texture, NO illustration style`.
- Add `CLEAN DIGITAL 3D GAME RENDERING`.
- Add `DIGITAL 3D GAME AESTHETIC - minimal surface detail`.
- Add `NO texture complexity, NO fine surface detail` to every material line.
- If the image still feels painted, repeat the fix inside `MATERIALS - LARGE FLAT COLOR BLOCKS` for every listed material, not only in the final negative prompt.

### Shadows are too complex

Symptoms: 5+ shadow bands, smooth realistic gradients, over-detailed occlusion, complex shadow shapes.

Fix:

- Rewrite each major element with: `<element> shading: <base> → <mid> → <shadow> (3 tones ONLY)`.
- Strengthen `3-4 level soft gradient shadows ONLY`.
- Strengthen `NO complex shadow shapes`.
- Keep the formulas concrete and element-specific. Do not leave generic phrases such as `stylized shadows` or `soft shading` without explicit color steps.

### Too cinematic, HDR, or realistic

Symptoms: dramatic rim light, hard contrast, black shadows, volumetric beams, photorealistic road/stone/water.

Fix:

- Strengthen `Soft LOW-CONTRAST lighting, NOT dramatic, NOT cinematic`.
- Add `Overall BRIGHT and clearly visible`.
- Replace realism terms with `simple flat illumination`, `blue-green atmospheric perspective`, and `large flat color blocks`.

### Text or UI dominates

Symptoms: giant travel title, poster headline, English UI, garbled readable text, app-style overlays.

Fix:

- Keep area discovery UI small or remove it. For rest/interior/terrace/close-up scenes, remove discovery UI and use only a small button prompt near the interactable object.
- Add `NO large center discovery title, NO poster heading, UI must not be the first visual read`.
- Require `main discovery label width under 30 percent of image width, height under 4 percent`.
- Require all readable UI to be Chinese.
- Convert signs and ads into unreadable Hyrule-like patterns or 1-3 character Chinese labels.
- Keep `HUD：按 TOTK 原版游戏实况自然出现，不堆满`.

### Material microdetail is too dense

Symptoms: leaves look photographic, stone walls have tiny cracks/pores, water has realistic ripple sparkle, fabric/wood has noisy patterns, city windows form dense grids, roads show tiny cars or lane markings.

Fix:

- Add the relevant `Scene-Specific Detail Suppression` line directly to `MATERIALS`.
- Add `Reduce all microdetail by 40-60 percent compared with the first pass`.
- Replace dense material descriptions with `broad sparse shapes`, `clustered stylized volumes`, `large flat panels`, `soft simplified color bands`.
- Keep only identity-giving rhythm: a few stone patches, a few facade lines, a few readable foreground leaves, not full photographic texture.
- Do not globally blur the image; keep silhouettes and gameplay objects crisp.

### City or landmark becomes concept art

Symptoms: ornate fantasy capital, too much gold decoration, Unreal/Octane promotional lighting, dense window grids, unrealistic glass reflections, skyline no longer matches reference, gliding scene looks like key art instead of gameplay.

Fix:

- Add `Preserve the reference landmark silhouette and city/bay/park/road relations; do NOT turn it into a generic fantasy capital`.
- Add `minimal gold accents only`, `broad simplified facade panels`, `NO dense windows`, `NO realistic reflections`, `NO ornate fantasy city poster`.
- Reduce cinematic light: `NO cinematic golden city glow`, `NO HDR`, `NO dramatic beams`.
- Keep Link/player character small as gameplay anchor with stamina UI, but preserve the high camera and route logic.
- Use blue-green atmospheric perspective to simplify distant skyline instead of adding decorative detail.

### Over-repaired or too clean

Symptoms: second pass is technically cleaner but weaker; Link becomes too small, camera changes, scene turns into a travel poster, weather density disappears, city/forest/village identity becomes generic, or environmental texture rhythm is over-simplified.

Fix:

- Reuse the first successful prompt structure and only patch the failed clause.
- Add `PRESERVE the first-pass camera angle, player-character scale, weather density, and reference composition`.
- Add `Do NOT recompose the scene; do NOT reduce environmental density; do NOT shrink the player character; do NOT remove the gameplay action`.
- For snow/rain/fog/city-sign scenes, preserve natural density as stylized game particles or panels rather than making the image empty.
- If UI is the only problem, fix only UI: `smaller subtle discovery UI, no poster title`, without changing the rest of the scene.

## Final Response

- For prompt-only requests, output only the final prompt code block.
- For image-generation requests, include a short note about what was generated and then include the concise generated prompt, unless the user explicitly asked for image only.
