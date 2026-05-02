# 图片素材生成提示词 (IMAGE_PROMPTS)

本文档记录了 FlyMacro 网站当前所用 SVG 占位素材的「未来栅格化版本」AI 生成提示词。
当你拥有了图像生成模型（Midjourney v6 / DALL·E 3 / Stable Diffusion XL / Flux 等）后,
可按下方提示词逐张生成 PNG/JPG/WebP, 然后替换 `static/images/` 下对应文件,
并把 `_index.md` / 各 `.md` 中的 `preview_img` 后缀改为 `.webp` 即可。

---

## 通用风格基线 (Base Style)

> Dark fantasy MMORPG concept art, World of Warcraft 2024 visual style, Blizzard art direction,
> matte painting, dramatic chiaroscuro, weathered gold filigree, runes, parchment textures,
> cinematic atmosphere, volumetric god rays, painterly brush strokes, no text, no logos.

负面词 (negative prompt):
> low-poly, plastic, neon, cyberpunk, anime, chibi, photo of real people, watermark, blurry, jpeg artifacts.

---

## 1. 首页头图 hero-bg.webp

**文件路径**: `static/images/hero-bg.webp` (1920×1080 或更高)

**提示词**:
```
Wide cinematic landscape from World of Warcraft, Stormwind ramparts at dusk seen from a high cliff,
distant snow-capped mountain ranges silhouetted against amber sunset, glowing magical orbs floating
above the valley, two tattered crimson banners with gold trim flanking the foreground,
runic stone circles half-buried in the earth, scattered embers and motes of light, fog drifting
between peaks, painted matte style, 21:9 aspect ratio, no characters, no text, dark fantasy.
```

**后续在 CSS 中替换** ([static/css/style.css:323-331](static/css/style.css#L323)):
```css
.hero::before {
  background:
    radial-gradient(...),
    url("/images/hero-bg.webp") center 30% / cover no-repeat,
    var(--bg-deep);
}
```

---

## 2. 章节背景纹理 parchment-bg.webp

**文件路径**: `static/images/ornaments/parchment.webp` (1024×1024 平铺无缝)

**提示词**:
```
Seamless tileable medieval parchment texture, aged vellum scroll, faded ink stains, subtle gold flecks,
slight wrinkles and creases, torn edges blended into pattern, dark sepia warm tones #1a1208 to #3a2814,
high resolution, used as a background overlay, no characters, no symbols.
```

---

## 3. 横幅装饰 banner.webp

**文件路径**: `static/images/ornaments/banner.webp` (transparent PNG, 800×220)

**提示词**:
```
Ornate medieval cloth banner ribbon, deep crimson velvet with gold embroidered trim,
fishtail ends curled, three-dimensional fabric folds with subtle highlights, isolated on transparent
background, centered composition, fantasy MMORPG UI element, side view.
```

---

## 4. 角部装饰 corner-ornament.webp

**文件路径**: `static/images/ornaments/corner.webp` (transparent PNG, 256×256)

**提示词**:
```
Ornate gold filigree corner bracket, baroque scrollwork with embedded ruby, intricate engraved metal,
worn aged finish, fantasy MMORPG inventory frame corner, transparent background, top-left orientation,
high contrast on dark background, no shadows.
```

---

## 5. 宝石分隔线 gem-divider.webp

**文件路径**: `static/images/ornaments/gem-divider.webp` (transparent PNG, 960×72)

**提示词**:
```
Symmetrical horizontal divider, two thin engraved gold filigree lines fading to transparent at the ends,
centered cut diamond gem (warm amber/topaz) with internal facets and subtle inner glow,
small accent dots flanking the gem, dark fantasy UI element, transparent background.
```

---

## 6. 13 职业徽章 classes/{slug}.webp

**文件路径**: `static/images/classes/{slug}.webp` (256×256 PNG, transparent background)

**通用包装提示词** (替换 `[CONCEPT]` 为下表内容):
```
Round metallic class crest emblem from World of Warcraft, [CONCEPT], engraved aged gold rim with
worn highlights, dark slate background inside the rim, isolated on transparent canvas, centered,
soft inner shadow, fantasy MMORPG icon, 1:1 aspect ratio, painterly detail.
```

| 职业 (slug) | [CONCEPT] |
|---|---|
| `deathknight` | snarling skull with frosted runeblade behind, icy blue glow in the eye sockets, frostmourne motif |
| `demonhunter` | demonic curved horn-helm with glowing fel-green slits, twin warglaives crossed below |
| `druid` | crescent moon embracing a leaf, vines and stars, soft orange-gold lunar light |
| `evoker` | ornate dragon eye with vertical slit pupil, bronze and emerald scales radiating outward |
| `hunter` | recurve bow with nocked arrow, hawk feather, forest-green tones |
| `mage` | eight-pointed arcane star with concentric rune circles, crystalline cyan glow |
| `monk` | jade yin-yang medallion within a lotus, mist and serpent-coil border |
| `paladin` | radiant warhammer over a holy sun, white-and-gold light rays, celestial glow |
| `priest` | feathered angel wings cradling a holy ankh, soft white luminescence |
| `rogue` | crossed jagged daggers behind a shadowed hood, drop of green poison on the blade tip |
| `shaman` | totem head crowned with feathers, lightning bolt, four elemental sigils on the rim |
| `warlock` | demonic skull within an inverted pentagram, sickly purple fel flames |
| `warrior` | two crossed broadswords behind a battered round shield, scarlet sigil at center |

---

## 7. 功能图标 icons/*.webp

**文件路径**: `static/images/icons/*.webp` (128×128 PNG, transparent)

提示词包装：
```
Stylized fantasy MMORPG UI icon, [CONCEPT], gold metal with worn highlights, ruby/sapphire accents
where appropriate, top-down 3/4 view, centered, isolated on transparent background, soft drop shadow.
```

| 图标 | [CONCEPT] |
|---|---|
| `scroll.webp` | rolled vellum scroll, three lines of mock script, red wax seal stamped with a flying dragon |
| `swords.webp` | two crossed long-swords, gold pommels with red gems, blades catching light |
| `dragon-eye.webp` | a single bronze dragon eye, slit pupil, scales fanning outward, soft inner glow |
| `shield.webp` | heater shield with two sword-cross emblem, golden rivets, deep wine-red field |

---

## 8. 宏配图 (article preview)

**文件路径**: `static/images/{slug}-preview.webp` (1280×720, JPG/WebP)

### priest-shadow-preview.webp (暗影牧师)

```
World of Warcraft Shadow Priest casting Mind Blast in a corrupted void cathedral,
purple shadow energy swirling around outstretched hands, eyes glowing white-violet,
ornate dark robes with skull motifs, gothic broken pillars, debris floating, blue-violet rim light,
cinematic close-up shot, painterly art style, no text overlay.
```

### priest-heal-preview.webp (神圣/戒律牧师)

```
World of Warcraft Holy Priest channeling Prayer of Healing inside a sunlit cathedral,
golden divine light radiating from raised hands, white-and-gold robes flowing, calm expression,
stained-glass windows in background, soft holy aura halos, warm cinematic light,
painterly art style, no text overlay.
```

### 其他职业模板 (复制改写)

替换以下变量后即可：
```
World of Warcraft [CLASS_NAME] [SPEC_NAME] in action, [SIGNATURE_ABILITY] cast effect,
[ENV_BIOME] background, [SIGNATURE_COLOR] energy theme, ornate class armor,
cinematic dramatic lighting, painterly art style, no text overlay.
```

| Class | Spec | Signature Ability | Color | Env |
|---|---|---|---|---|
| Mage | Frost | Frostbolt | icy blue | snowy ruined keep |
| Mage | Fire | Combustion | molten orange | burning library |
| Hunter | Beast Mastery | pet roar with leashed beast | forest green | jungle clearing |
| Warrior | Arms | Mortal Strike | crimson red | gladiator arena |
| Paladin | Retribution | Wake of Ashes | radiant gold | sunlit battlefield |
| Druid | Restoration | Tranquility | nature green | enchanted glade |
| Rogue | Subtlety | Shadow Dance | smoky purple | back-alley night |
| ... | ... | ... | ... | ... |

---

## 9. 网站 Logo / Favicon

**文件路径**: `static/images/logo-512.webp` + `static/favicon.ico` (32x32 / 64x64 / 256x256)

**提示词**:
```
Minimal heraldic gold shield silhouette, central winged sword pointing up, no text,
flat icon style with subtle aged metal texture, isolated on dark slate background, square 1:1.
```

---

## 替换工作流 (Workflow)

1. 用上述提示词在 Midjourney / DALL·E / Flux 生成 4 张候选, 选 1 张最合适。
2. 用 [squoosh.app](https://squoosh.app) 转 WebP, 质量 85, 4:2:0 子采样。
3. 把生成的图直接覆盖到 `static/images/` 对应路径, **不要改文件名**, Hugo 会自动重新构建。
4. 如果文件后缀变了 (svg → webp), 同步更新:
   - 各 macro `.md` 的 `preview_img` 字段 (`content/zh/macros/...`)
   - `static/css/style.css` 中 `hero::before` 的 `url(...)`
5. 生成后 `npx --yes hugo-bin --minify` 检查无 404。

---

## 风格一致性检查清单

- [ ] 所有图片色调统一在「深色 + 金色 + 暗红」主调
- [ ] 所有职业徽章的金属边缘风格一致 (磨损/抛光程度)
- [ ] 所有宏配图取景距离一致 (中近景半身像)
- [ ] WebP 质量在 80-85, 单文件 < 200KB (hero 除外)
- [ ] 没有任何水印 / AI 签名 / 可见文本
