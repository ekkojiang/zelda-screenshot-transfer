---
name: zelda-screenshot-transfer
description: "Transform real-world reference photos into concise The Legend of Zelda: Breath of the Wild or Tears of the Kingdom Nintendo Switch in-game screenshot prompts or generated images. Use when the user provides landscape, town, castle, mountain, street, village, ruin, desert, lake, forest, travel, or architecture photos and asks for Zelda/BOTW/TOTK screenshot transfer, prompt generation from reference images, image-to-image prompt writing, 9:16 mobile covers, Link as the single player character, dynamic gameplay moments based on scene and camera angle, original HUD, Chinese area discovery UI, Zonai shrines, original-style treasure chests, monsters, NPC conversion, or reusable photo-to-Zelda prompt workflows."
---

# 塞尔达实况转绘

中文名：塞尔达实况转绘

Convert real-world reference photos into BOTW/TOTK-style Nintendo Switch gameplay screenshots.

This skill is a **photo transfer workflow**. For the final prompt style, follow the concise structure of `zelda-style-image-prompt`: one strong style anchor, short fields, gameplay language, and compact element lists. Do not write long cinematic, material, or camera essays.

Recent calibration target: prefer the cleaner real-place result over generic invented labels and the low-frequency, pale, soft Nintendo Switch in-game look. The best outputs keep the reference location recognizable, choose Link's gameplay action from the scene content and camera angle, use the true place name when known, include a subtle original-style area discovery UI, keep HUD light, reduce tiny brush marks and photo textures, and avoid poster-size UI text or readable real-world signage.

## Disclaimer

This is a fan-made, non-commercial skill for personal learning, research, and workflow testing only. It is not affiliated with, endorsed by, sponsored by, or approved by Nintendo, The Legend of Zelda, Breath of the Wild, Tears of the Kingdom, or any related rights holders.

All trademarks, game names, characters, visual references, and related intellectual property belong to their respective owners. Do not use this skill, its prompts, or generated outputs for commercial sale, advertising, merchandising, paid services, or any use that may imply official authorization.

Users are responsible for ensuring their own use complies with copyright, trademark, platform, and local legal requirements. This notice is not legal advice.

中文说明：本 skill 仅用于个人学习、研究和非商业工作流测试，不作为商业用途，不代表任天堂或《塞尔达传说》系列官方授权。请勿将提示词或生成结果用于售卖、广告、周边、付费服务或任何可能让人误认为官方授权的场景。

## Output Mode

- If the user asks to **generate images**, use the image generation workflow available in the environment.
- If the user asks for **prompts**, return reusable prompts.
- If the user asks to **generate images from a reference photo**, generate first, then also provide the final generated prompt unless the user explicitly asks for image only.
- If the user asks for both, generate first, then provide the prompt.
- For prompt-only tasks, return the final prompt in one code block unless the user asks for explanation.

## Prompt Generation Function

When a reference image is provided, always derive a concrete prompt from that image. Do not output placeholders such as `[参考图核心结构]`, `[真实地名]`, or `[3-5 个关键词]`.

Use the user's requested subject, companions, special elements, and UI text when provided. Otherwise choose scene-appropriate defaults from the reference image.

Prompt-only output must use one Chinese code block with this field order:

```text
塞尔达原版游戏实况截图复刻
画风：任天堂 Switch 旷野之息/王国之泪实机游戏截图风格；不要电影 CG、不要写实摄影、不要 HDR 真实光影、不要湿润真实材质
TOTK 王国之泪默认造型，林克单人
画面尺寸比例：9:16

参考图：保留<原图核心构图、主体、环境和关键道具>
海拉鲁地图区块：<真实地点名 / 场景名 / 主题名>
画面要素：<3-5 个可识别关键词>
玩法时刻：<根据画面内容和镜头机位选择动作；写清是否消耗体力和是否显示耐力轮>

塞尔达元素：<3-7 个场景适配元素>
地名 UI 文字（区域发现）：顶部「发现！」 / 中间「<地名>」 / 底部「<国家·城市/地区或上级区域>」；按原版区域发现三段式呈现，底部上级区域右对齐、只在文字左侧带短横线、淡色发光、无矩形边框、无深色底纹
HUD：按 BOTW/TOTK 原版游戏实况自然出现，不堆满
文字：所有可读 UI 使用中文，按键动词只用中文，如「调查」「打开」「拾取」「烹饪」
```

If the user explicitly asks for Zelda or another companion, change the character line and gameplay sentence accordingly, for example `TOTK 王国之泪默认造型，林克和塞尔达`. Otherwise keep Link single.

For image-generation output, include the same generated prompt in the final response after the image note. Keep it concise and usable as a direct image2 prompt.

## Reference Analysis

Before prompting, identify only what affects the transfer:

- Core subject: castle, street, mountain, lake, desert, village, ruins, forest, etc.
- Recognizable features to preserve: skyline, building silhouette, terrain shape, water path, road, bridge, cloud pattern, tree line.
- Best gameplay action from the scene and camera: running, walking, climbing, shield-surfing, gliding, sneaking, swimming, observing, fighting, talking, resting, cooking, sleeping.
- Scene-appropriate Zelda elements: shrine, treasure chest, enemy camp, merchant, research NPC, boat, stable, cooking pot, cave, tower, sky ruin.
- Modern people or objects that must be converted or removed.
- Real-place confidence: exact landmark/city if visible or supplied, likely region if inferable, or unknown.

Preserve the reference photo's identity. Improve it into a playable game moment, not a poster.

## Prompt Shape

Use short Chinese prompts in this order:

```text
塞尔达原版游戏实况截图复刻
画风：任天堂 Switch 旷野之息/王国之泪实机游戏截图风格；不要电影 CG、不要写实摄影、不要 HDR 真实光影、不要湿润真实材质
TOTK 王国之泪默认造型，林克单人
画面尺寸比例：9:16

参考图：保留[参考图核心结构]，现代设施和游客做海拉鲁化转译；草地、树叶、山石、屋顶、墙面和水面统一为低频大色块，减少细碎笔触和照片纹理
海拉鲁地图区块：[真实地点名 / 场景名 / 主题名]
画面要素：[3-5 个可识别关键词，只列名词或短词组]
玩法时刻：[根据画面内容和镜头机位选择林克动作；一句话写林克正在做什么；体力动作写「正在消耗体力，显示耐力轮」，非体力动作写「不消耗体力，不显示耐力轮」]

塞尔达元素：[3-7 个关键词，只列名称，不展开外观]
地名 UI 文字（区域发现）：顶部「发现！」 / 中间「[真实地名]」 / 底部「[国家·城市/地区]」；按原版区域发现三段式呈现，主地名宽度不超过画面 40%、高度不超过画面 6%，底部国家·城市/地区右对齐、只在文字左侧带短横线、淡入式小字、淡色发光、无矩形边框、无深色底纹，不占据天空主视觉
HUD：按 BOTW/TOTK 原版游戏实况自然出现，不堆满
文字：所有可读 UI 使用中文，按键动词只用中文，如「调查」「打开」「拾取」「烹饪」；场景内招牌优先转为不可读海拉鲁纹样或极短中文，不生成长店名、广告字、乱码、英文
```

Keep prompts around 10-13 lines. Do not add foreground/midground/background breakdowns, lens specs, material paragraphs, or long lighting descriptions.

## Style Anchor Rules

Always use these first two lines exactly:

```text
塞尔达原版游戏实况截图复刻
画风：任天堂 Switch 旷野之息/王国之泪实机游戏截图风格；不要电影 CG、不要写实摄影、不要 HDR 真实光影、不要湿润真实材质
```

Do not scatter technical style words across the prompt. Do not add extra phrases like `cel-shading 扁平卡通色块`, `强黑描边`, `柔光绘画感`, `非 PBR`, or long material descriptions outside the `画风` line unless the user explicitly asks for diagnostic detail.

## In-Game Visual Calibration

Use the user's BOTW/TOTK screenshots as the visual target:

- Overall image is bright, saturated, soft, lightly hazy, and game-rendered, not glossy or photographic.
- Use BOTW/TOTK-like clean daylight: clear blue sky, warm sunlit color planes, vivid greens/yellows/blues, and readable soft highlight bands.
- Grass appears as clean bright color masses with a few readable blades near the camera, not thousands of realistic strands.
- Trees and leaves appear as clustered stylized volumes, not individually detailed leaves.
- Rocks, roofs, walls, roads, floors, and water use low-frequency hand-painted texture blocks, not photo texture, scratches, pores, asphalt grain, or tiny brush marks.
- Shadows are thin, soft, and colored; use stylized game contrast and stronger art-directed color saturation, but avoid hard black contact shadows, HDR realism, and photographic exposure.
- Distant mountains, buildings, and trees are lighter, bluer, softer, and lower contrast.
- Character and interactable props have clear game silhouettes and smooth shaded color planes.

If a generated image drifts toward glossy fantasy illustration, HDR realism, dull washed-out color, or highly detailed PBR textures, iterate by keeping the exact style anchor and simplifying the rest of the prompt. Add one short transfer sentence: `整体明亮清爽、色彩饱和、光影柔和但更有游戏美术层次，草地、树叶、山石、屋顶、墙面和水面是低频大色块，减少细碎笔触和照片纹理`.

Avoid these output failures:

- poster-like fantasy key art
- oversized title text covering the sky
- readable tourism signs or shop names becoming the visual focus
- glossy wet stone, hard black shadows, realistic road asphalt, detailed leaf/grass microtexture
- fragmented painterly brush strokes, scratchy texture, noisy foliage, realistic wall/roof/stone grain
- dull gray color, muddy lighting, overexposed HDR glare, photorealistic shadow contrast
- UI that looks like a mobile app overlay instead of a gameplay screenshot

## Character Rules

- Default: `TOTK 王国之泪默认造型，林克单人`.
- If the user explicitly asks for BOTW, use `BOTW 旷野之息默认造型，林克单人`.
- If the user asks for Zelda or companions, follow that request. Otherwise do not add Zelda, companions, duplicate Link, or unrelated heroes.
- Do not describe Link's clothing, hair, shield, sword, face, or gear in detail. The game/version anchor handles the default look.
- If the reference photo contains modern pedestrians, tourists, seated people, workers, cars, signs, or barriers, convert only those reference-photo items into Zelda-world equivalents or remove them. This rule must not replace Link.

NPC conversion examples:

- Tourists -> 海利亚村民 / 旅行商人 / 驿站旅人 / 希卡族研究员
- Staff -> 巡逻守卫 / 研究员 / 驿站老板
- Plastic signs / railings -> 木牌 / 石碑 / 古代机关 / 栅栏
- Vehicles / modern facilities -> 马车 / 木筏 / 驿站 / 机关平台

Avoid modern clothing, realistic tourists, uniforms, cars, phones, logos, and readable real-world signs.

## Real Place Naming

Use the strongest available real-place name for readable area UI.

- If the user names a place or the reference clearly depicts a known landmark, use that true Chinese place name as the middle UI line: `阿苏山`, `班贝格`, `罗滕堡`, `科尔多瓦清真寺`, etc.
- Use the true upper region as the bottom UI line when known: `日本·熊本`, `德国·巴伐利亚`, `法国·奥克西塔尼`, etc.
- Do not replace a known place with a generic invented label such as `火山山脚驿路`, `古堡山道`, or `湖边遗迹` in readable UI. Generic names are allowed only when the real location is unknown.
- If location confidence is low, either omit the area discovery line for image generation or use a neutral scene name without pretending it is a real place.
- `海拉鲁地图区块` may include a gameplay-flavored subtitle, but readable UI should stay true to the real place when known.

## Gameplay Moment Rules

Choose Link's gameplay moment from the reference content and camera angle. Write one clear gameplay sentence. Use simple verbs, not body micro-details.

Action selection:

- Roads, village paths, bridges, town streets -> walking, running, talking to a merchant, or observing a landmark.
- Cliffs, castle walls, towers, ruins, steep rocks -> climbing or preparing to climb.
- High overlooks, valleys, cloud seas, mountains, rooftops -> gliding or preparing to glide.
- Snow slopes, sand dunes, long downhill paths -> shield-surfing.
- Campsites, campfires, tents, inns, warm night scenes -> resting, cooking, sleeping, or watching the sky.
- Water, rivers, lakes, coasts -> swimming, rafting, standing on a shore, or watching a hidden chest.
- Meadows, animals, quiet scenic views -> walking, observing, riding, or taking a calm rest.
- Enemy camps, ruins with patrols, narrow alleys -> sneaking, fighting, or observing from cover.

Camera matching:

- Wide aerial or high-angle views should usually make Link small and action-led, such as gliding, running along a path, or observing from above.
- Low-angle architecture or rock shots should use climbing, approaching, or looking up.
- Third-person road or village shots should use walking, running, talking, or interacting.
- Close camp or interior shots should use cooking, resting, sleeping, opening a chest, or talking.

Do not default to Link standing centered in the foreground. The action should make the reference photo feel like a playable moment.

Good actions:

- `林克沿村道奔跑，不消耗体力，不显示耐力轮`
- `林克攀爬城堡外墙，正在消耗体力，显示耐力轮`
- `林克张开滑翔伞越过峡谷，正在消耗体力，显示耐力轮`
- `林克在沙丘上盾滑冲向水湾，不消耗体力，不显示耐力轮`
- `林克观察远处敌人营地，不消耗体力，不显示耐力轮`
- `林克在篝火旁烹饪，不消耗体力，不显示耐力轮`
- `林克在帐篷旁休憩并仰望夜空，不消耗体力，不显示耐力轮`
- `林克在旅店床铺上睡觉，不消耗体力，不显示耐力轮`

Do not write frame-by-frame body mechanics, exact limb positions, stamina percentage, or camera lens language.

## Zelda Elements

Choose 3-7 scene-appropriate names only. Do not explain appearance, material, or location unless the user specifically asks.

Element pool:

- Exploration: `TOTK 左纳乌神庙`, `原版神庙`, `鸟望台`, `高塔`, `天空遗迹`, `古代石门`, `山洞入口`, `传送台`, `女神像`
- Props: `原版宝箱`, `料理锅`, `篝火`, `木桶`, `矿石`, `武器架`, `木筏`, `滑翔伞`, `马匹`, `风扇`, `火箭`, `热气球`, `左纳乌装置`
- Enemies: `波克布林`, `蜥蜴怪`, `莫力布林`, `人马`, `丘丘`, `骷髅怪`, `岩石巨人`, `方块魔像`, `飞行魔物`
- NPCs: `海利亚村民`, `旅行商人`, `驿站老板`, `希卡族研究员`, `巡逻守卫`
- Environment gameplay: `敌人营地`, `巡逻路线`, `可攀爬岩壁`, `湖中隐藏宝箱`, `破碎吊桥`, `解谜石碑`, `机关门`

Use elements because they fit the photo:

- Water / desert / cliffs -> `蜥蜴怪`, `木筏`, `湖中隐藏宝箱`, `TOTK 左纳乌神庙`
- Meadows / roads / villages -> `旅行商人`, `原版宝箱`, `波克布林营地`, `马匹`
- Ruins / castles / mountains -> `原版神庙`, `高塔`, `可攀爬岩壁`, `飞行魔物`
- Camps / stables / village edges -> `料理锅`; do not put a cooking pot randomly in the middle of a street, desert, or open meadow.

## HUD And Chinese UI

- HUD line should stay short: `HUD：按 BOTW/TOTK 原版游戏实况自然出现，不堆满`.
- Do not specify HUD position, exact shape, count, arrangement, icon style, minimap details, or stamina amount.
- Mention stamina only inside the gameplay sentence as `正在消耗体力，显示耐力轮` or `不消耗体力，不显示耐力轮`.
- All readable UI text must be Chinese.
- Button verbs must be Chinese only, such as `调查`, `打开`, `拾取`, `烹饪`.
- Allowed button verbs include: `攻击`, `对话`, `调查`, `拾取`, `打开`, `攀爬`, `滑翔`, `跳跃`, `潜行`, `蓄力`, `瞄准`, `骑乘`, `丢出`, `烹饪`, `装备`, `休息`, `睡觉`.
- Avoid English UI words, garbled text, subtitles, watermarks, app-style labels, QR codes, and tourism-poster titles.
- For image generation, avoid adding extra readable in-scene text unless it is essential. Convert storefronts, banners, road signs, hotel names, and real ads into unreadable Hyrule-like patterns, simple icons, or 1-3 character Chinese labels.
- Keep HUD lighter than the scenery. Do not ask for every HUD component at once; let the game screenshot anchor handle natural HUD density.

## Area Discovery UI

For image generation and prompt-only transfer, add one subtle area discovery UI line by default unless the user explicitly asks for no UI.

Use real Chinese names when the photo depicts a known real place. If the place is unknown, use a simple scene name such as `白沙丘水湾`, `山间古堡`, `雪岭驿站`, `湖边遗迹`, and use the best known broader region only when it is not fabricated.

Template:

```text
地名 UI 文字（区域发现）：顶部「发现！」 / 中间「<真实地名>」 / 底部「<国家·城市/地区>」；按原版区域发现三段式呈现，主地名宽度不超过画面 40%、高度不超过画面 6%，底部国家·城市/地区右对齐、只在文字左侧带短横线、淡入式小字、淡色发光、无矩形边框、无深色底纹，不占据天空主视觉
```

Do not put game-world place names such as `海拉鲁`, `格鲁德高地`, `卡卡里科村`, or `海拉鲁城堡` into readable UI text unless the user explicitly asks for a pure in-game Zelda location.

When area discovery UI is included in an image prompt:

- Prefer true real-place middle text, e.g. `阿苏山`, not a generic gameplay label.
- Bottom text should use `国家·城市/地区`, e.g. `日本·熊本`, `德国·巴伐利亚`, `法国·奥克西塔尼`.
- Never output the literal placeholders `地名` or `国家·城市`; replace them with the specific place or a non-fabricated neutral scene label.
- Keep it subtle and screenshot-like: main place name width <= 40% of image width, height <= 6% of image height, fade-in small text, and never occupy the main sky view.
- Do not make it a giant poster title, travel-title overlay, or cover headline.
- Do not add extra decorative labels, subtitles, travel slogans, or shop-sign text.

## Size And Format

Default for mobile vertical covers:

```text
比例：9:16 手机竖屏
目标分辨率：2K，例如 1440x2560
```

Keep this as execution guidance. Do not force it into the concise prompt if the image tool already receives size controls or if the user only asks for a text prompt.

## Generation Workflow

When generating from a reference photo:

1. Analyze the photo briefly.
2. Decide whether the real place is known. If known, use the true Chinese place name in readable UI; if unknown, avoid fake specificity.
3. Add one area discovery UI line by default; keep it subtle, true to the known location, and in the `顶部「发现！」 / 中间「地名」 / 底部「国家·城市/地区」` structure.
4. Build the concise generated prompt using the template above, replacing every placeholder with concrete content from the reference image.
5. Generate the image if requested.
6. For image-generation requests, include the generated prompt in the final response unless the user explicitly asks not to.
7. If the result looks too realistic, too brushy, too gray, or weak in art direction, keep the exact `画风` line and add the one short saturation/light transfer sentence from In-Game Visual Calibration. Do not fix realism by adding long material paragraphs.
8. If HUD is wrong, keep the HUD line simple and iterate image output; do not over-specify HUD geometry.
9. If text is messy or too dominant, remove area discovery UI and ask for in-scene signs to become unreadable patterns or short Chinese labels.

## Checklist

Before delivering a prompt or image, check:

- Does the prompt start with the exact style anchor?
- Is the prompt around 10-13 lines, not a long essay?
- Are all template placeholders replaced with concrete content from the reference image?
- Does it preserve the reference photo's recognizable features?
- Is Link single unless the user explicitly requested otherwise?
- Are modern people and objects converted or removed?
- Are Zelda elements listed as compact names, not appearance descriptions?
- Is the gameplay sentence clear and does stamina match the action?
- Is the HUD instruction short and non-positional?
- If area UI appears, is it true to the real location, small/subtle, Chinese, and not using Zelda in-game place names for real-world photos?
- Are shop signs, banners, ads, and road signs converted to non-readable patterns or very short Chinese labels instead of long text?
- Are grass, foliage, stone, roof, wall, floor, and water simplified into low-frequency game texture blocks instead of tiny brush marks or photo texture?
- Is the image bright and saturated with stylized soft game lighting, not dull, muddy, HDR, or photographic?
- Does the prompt avoid photorealism, movie CG, HDR, and wet realistic materials?

## Final Response

- For prompt-only requests, output only the final prompt code block.
- For image-generation requests, include a short note about what was generated and then include the concise generated prompt, unless the user explicitly asked for image only.
