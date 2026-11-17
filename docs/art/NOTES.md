# 必須アート10枚 — round 1

制作日: 2026-11-17（Asia/Tokyo）。BRIEFは全文確認。REVIEW.mdは存在しなかったため必須10枚のみ制作。「できれば」の素材とゲームコードは変更していない。

## 生成方法・原本の所在

全10枚を会話の組み込み画像生成機能 `image_gen.imagegen` で1枚ずつ新規生成。CLI/API代替、ローカル画像モデル、SVG、Canvas、図形描画、生成ノイズは使用していない。

原本ディレクトリ（画像生成機能の保存通知に基づく。原本は保持）:

`C:\Users\manga\.codex\generated_images\01a1e9e8-461c-7480-ad47-d690fbd8e03a\`

| 納品ファイル（public/game/assets/） | ツールが保存した原本名 | 再生成回数 |
|---|---|---:|
| ship.png | call_RlR30X8dUeERmC4sk57xic8Y.png | 0 |
| rock_iron_1.png | call_nMf4yOTUnorKT9dDWZkoYaUI.png | 0 |
| rock_iron_2.png | call_ntTnJ9b4Rc9kFUIFaYyyat85.png | 0 |
| rock_ice_1.png | call_pkU5PW9Zfu6dkAcZahUMX4Gq.png | 0 |
| rock_ice_2.png | call_U7DFriks34WgAa77yVJCo5sj.png | 0 |
| rock_crystal_1.png | call_JmoYs7La8bNHsZyuflj7AOIy.png | 0 |
| rock_crystal_2.png | call_arR16V6K4lvhQ6tFSrllVCju.png | 0 |
| comet.png | call_93PvOirBU8rNxvLXREblC6y6.png | 0 |
| far.png | call_NMSzvwxnAzSGKH51jTYJ0Tq2.png | 0 |
| bg.jpg | call_44VypW2MIrXiPG4IkCCQVYWa.png | 0 |

スプライト原本は1254×1254 RGBA、背景原本は1448×1086 RGB。背景の2048×1536化はアップスケールでありネイティブ生成ではない。seed指定パラメータは組み込みツールに公開されていない。今回は編集の連鎖も再生成もなく、seedの固定・再利用はしていない。

## 許可範囲の後処理

Pillow 12.3.0で生成済みピクセルの縮小・トリミング・透過整理・形式変換・一覧配置のみ実施。描き足し、模様生成、輪郭の作画はしていない。

実アルファを保持し、余白に散在するアルファ値8以下のほぼ透明なピクセルのみ透明化。透明余白をトリミングし、縦横比を保ったLANCZOS縮小で最長辺436px（85.16%）として512×512の透明キャンバス中央に配置。PNGはRGBAのままロスレス保存し、減色なし。黒抜き・緑抜きは不要だった。背景は4:3を維持して2048×1536へLANCZOS拡大し、JPEG品質90・色差サブサンプリングなしで保存。

`preview.png` は #060818 の暗い背景上に全10枚を配置。9スプライトを256pxキャンバスで並べ、背景は768×576。鉱石6枚は別途64×64キャンバスで並べ、船の110pxキャンバス表示も配置。名前ラベルは一覧だけに付け、素材自体には文字なし。透明余白込み64pxなので、ゲームの余白切詰め後64px表示より対象はやや小さい。

## 個別目視・気になる点

画像生成機能が表示した原本10枚をそれぞれ個別に目視した。以下の作画・内容の判定は原本に対するもの。最終PNG/JPGをview_imageで再表示しようとしたが、環境の `helper_sandbox_lock_failed / SetNamedSecurityInfoW ... failed: 5` で失敗。Node画像表示もカーネル終了、代替表示環境も同じsandbox障害で利用できなかった。**後処理済み画像・preview.png・最終64px表示の再目視は未完了**であり合格済みとは扱わない。後処理後の寸法・容量・透過・配置・縦横比は数値検査した。

| 画像 | 原本で個別に確認した内容 | 気になる点 |
|---|---|---|
| ship.png | 上向き、真上より少し後方の視点、左右対称の機体構造、明灰色、上部採掘口・下中央ノズル、炎なし、左上光、全機が収まる | 汚れや照明は完全鏡像ではない。110px完成表示の再目視は未完了 |
| rock_iron_1.png | 丸いごつごつした岩、大きな左上クレーター、橙の非溶岩鉱脈、左上光 | 細かいピットは小表示で省略される見込み。64px再目視は未完了 |
| rock_iron_2.png | 上辺のくぼみ・左下の張り出しがある別輪郭、小クレーター群、橙鉱脈、左上光 | 同一鉱種として色調は1に近づけている。64px再目視は未完了 |
| rock_ice_1.png | 丸い氷塊、青白い半透明層・霜・気泡、自然な割れ目、左上光 | 彗星との差は主にシアン色と結晶形状。64px再目視は未完了 |
| rock_ice_2.png | 二つの上部こぶ・右側のくぼみ、層状の氷と霜、1と異なる輪郭、左上光 | 微細な氷層は小表示で簡略化される見込み。64px再目視は未完了 |
| rock_crystal_1.png | 暗い岩から複数の紫結晶、内部発光、全体は丸い、左上光 | 紫の内部発光は意図的。64px再目視は未完了 |
| rock_crystal_2.png | 中央ジオード状の密集結晶、岩の太い下縁、1と異なる輪郭、左上光 | 結晶面積が1より大きく鉱種内に明度差がある。64px再目視は未完了 |
| comet.png | 白い氷と短い結晶、通常の氷より白く明るい、尾・粒子なし、左上光 | 64pxでの通常氷との明度差の再目視は未完了 |
| far.png | 全体が暗く左上の縁付近だけ青白く照らされ、右下は暗い、全体が収まる | ゲーム側でさらに暗くすると細部が消える可能性 |
| bg.jpg | 星雲は上左右、上部に淡い小惑星帯、中央〜下部は暗く静か、大惑星・中央の明るい星なし | 原本から拡大したため細密感に限界。中央下にもごく淡い微小星はある |

## BRIEFチェックリスト

- [x] 原本10枚を個別に目視し、図形の組合せでなく描き込まれた質感を確認。
- [x] 原本同士を比較し、写実寄りハードSFの質感・寒色光・控えめな彩度を統一。
- [x] 原本それぞれで左上光を確認。結晶は指示どおり内部発光もある。
- [ ] 最終64pxで鉄・氷・結晶を色と形で識別できるか再目視。一覧に縮小済みだが表示環境障害により未完了。
- [x] 船の原本で機首が上向き、炎なしを確認。
- [x] 原本で対象の欠けなしを目視し、最終9PNGの実アルファ・透明余白を数値確認。
- [x] 原本それぞれに文字・ロゴ・枠・UI・透かし・署名なしを目視。
- [x] 背景原本の中央から下に明るい物なしを目視。
- [x] 最終ファイル名・寸法・形式・容量を検査。PNGは400,000バイト以下、JPEGは700,000バイト以下という厳しい十進基準。
- [ ] preview.png全体を開き、統一感と合成縁を最終目視。作成済みだが表示環境障害により未完了。

## 最終ファイルの数値検査

| ファイル | 寸法 | 容量（バイト） |
|---|---|---:|
| ship.png | 512×512 | 253673 |
| rock_iron_1.png | 512×512 | 364646 |
| rock_iron_2.png | 512×512 | 352256 |
| rock_ice_1.png | 512×512 | 355473 |
| rock_ice_2.png | 512×512 | 352236 |
| rock_crystal_1.png | 512×512 | 371097 |
| rock_crystal_2.png | 512×512 | 357810 |
| comet.png | 512×512 | 322926 |
| far.png | 512×512 | 259232 |
| bg.jpg | 2048×1536 | 182898 |

9PNG全てがRGBA、アルファ範囲0〜255、外周透明。実体最長辺436px、外周余白は最低38px。小惑星類の実体縦横比は最大1.0583で1.25以下。全画像をPillowで再デコードして破損なしを確認した。

bg.jpg下半分の平均輝度は5.313/255、最大47/255。preview.pngは1536×1576、1,143,663バイト、背景色(6,8,24)を検査。数値検査は目視の代わりではないため、上記の未完了項目は残している。

## 生成プロンプト

以下は各画像生成ツール呼び出しに渡した全文。全て初回採用、作り直し0回。

### ship.png

```text
Create ONE final production game sprite, ship.png. Square canvas, genuinely transparent background (real alpha, not a drawn checkerboard), no backdrop, no ground or cast shadow. Hard science-fiction concept-art digital PAINTING, realistically hand-painted intricate industrial materials, restrained saturation, not vector, not low-poly, not anime, not a cheap CGI render, not a toy. Strong cool blue-white directional light from upper left; deep lower-right shadows with extremely thin muted violet rim on object only. A compact stocky SMALL INDUSTRIAL MINING WORKBOAT, bright light-gray worn metal hull so silhouette reads against dark space. Bilaterally symmetric geometry about the VERTICAL centerline. Camera almost directly overhead, slightly from behind, seeing a little of rear faces; absolutely NO yaw or diagonal rotation. The blunt short nose points exactly UP, toward 12 o'clock. Broad blunt side equipment pods, utilitarian work vessel, NOT a fighter, NO swept wings, no guns. One unmistakable mining-beam aperture at center of top/nose, UNLIT; one dark engine nozzle exactly centered at the rear/bottom edge, UNLIT. No flames, exhaust, beam, particles, text, logo, signature, watermark, UI, frames, labels. One complete vessel centered, maximum extent approximately 85% of square, generous transparent margin all around, no cropping. Rich painted scuffs and panel detail but broad readable forms at 110px tall. Produce only this single sprite.
```

### rock_iron_1.png

```text
Create ONE production game sprite rock_iron_1.png, a complete isolated iron-rich asteroid. Square canvas with genuinely TRANSPARENT background, real alpha, no background painting, no ground, no cast shadow, no glow spill. Hard-SF concept-art digital painting with rich realistically painted natural material, tactile pitted charcoal basalt and rusted metal; restrained saturation, NOT vector, not low-poly, no polygon facets, not anime, no cheap CGI or toy look. Strong slightly blue-white light exclusively from upper LEFT; deep shadow at lower right and a very thin faint violet rim on the object. A squat broadly ROUND irregular asteroid, width/height between 0.9 and 1.1, distinctly lumpy with a broad shallow impact crater high on left and smaller cavities, jagged silicate ridges. Recognizable rusty ORANGE metal ore veins using #ffa25c, rough oxidized metallic seams embedded within dark gray rock, orange is reflected pigment NOT glowing lava. No glowing fracture VFX, no fragments or particles, no lettering, logos, border, UI, watermarks or signature. Center the single complete rock occupying approximately 85% maximum canvas dimension with empty transparent margin all around. The bold round silhouette and several broad orange seams must read at 64 pixels. Fine natural painted surface texture, cohesive game concept art.
```

### rock_iron_2.png

```text
Create ONE production game sprite rock_iron_2.png, a complete isolated iron asteroid, variant TWO with a DISTINCT silhouette. Square genuinely TRANSPARENT real alpha background, no backdrop, no cast shadow, no glow spill, no floating fragments. Hard science-fiction concept-art digital PAINTING, realistically painted tactile natural geology and intricate pitted oxidized metal, restrained saturation; NOT vector, not low-poly, not anime, not a cheap CGI render, not a toy. Strong cool blue-white directional light from UPPER LEFT, deep lower-right shadow, extremely thin muted violet rim confined to rock. Single broadly ROUND knobbly boulder, width/height nearly 1:1 and no more than 1.15, irregular compact five-lobed outline with a flattened notched top and a broad projecting lower-left shoulder, unlike an oval. Several overlapping SMALLER impact craters cluster on the upper-left illuminated face; rough folded ridges, dense charcoal basalt. Broad rusty ORANGE metallic ore bands #ffa25c cross from upper left toward lower right, rich ochre exposed metal around the crater rims. Ore is oxidized material, NOT molten lava and no VFX cracks. Texture must look richly painted, not assembled simple shapes. Center complete rock at about 85% of square maximum extent, transparent margin all sides, no clipping. Clear orange versus charcoal read even at 64px. No text, logo, labels, border, frame, UI, signature, watermark.
```

### rock_ice_1.png

```text
Create ONE final production game sprite rock_ice_1.png. Complete isolated icy asteroid on a square genuinely TRANSPARENT real-alpha canvas, no painted backdrop, no ground, no cast shadow, no aura or loose fragments. Hard-SF concept-art digital PAINTING, richly detailed believable natural material, cohesive realistic painted texture not vector, low-poly, anime, toy or cheap CGI. Strong slightly blue-white key light from upper LEFT, deep lower-right shadow with extremely thin muted violet rim confined to object. A massive compact broadly ROUND blue-white ice boulder, irregular almost circular contour, width/height near 1:1 (never over 1.2), broad uneven five-sided natural outline, NOT a perfect sphere. Cyan #8fe3ff within layered SEMITRANSPARENT ice, thick frosted white crust, cloudy compressed strata, small entrapped bubbles, several broad jagged natural fissures that reveal deeper blue ice. Jagged ice faces are organic fracture surfaces, not polygon mesh. No protruding long crystal spikes; distinguish from purple crystal ore by rounded compact mass and frosty cyan-white coloration. Strong sculptural light upper left, shadows lower right. Single whole object centered, roughly 85% maximum canvas extent, empty transparent margins all around, unclipped. Recognizable pale cyan ice at 64 pixels. No particles, glow effects, text, logos, frames, UI, labels, signature or watermark.
```

### rock_ice_2.png

```text
Create ONE final production game sprite rock_ice_2.png, second distinctive icy asteroid silhouette. Square canvas, genuinely TRANSPARENT background real alpha, no backdrop, no ground or cast shadow, no aura or detached particles. Hard-SF concept-art digital PAINTING, realistically painted natural material with fine frost and surface texture, restrained saturation, NOT vector, low-poly, anime, cheap CGI or toy. Strong blue-white directional key light from upper LEFT, deep lower-right shadows, exceptionally thin subdued purple rim confined to object. Compact approximately ROUND glacier-ice boulder with width/height nearly 1:1, always below 1.2. Different from a simple rounded ice ball: squat chunky crag with two thick blunt peaks on top, a recessed notch on right flank, and a wide scalloped lower edge. Large overlapping thick curved translucent blue-white ice slabs sweep diagonally from upper right toward lower left like compressed stratified glacier ice, broad cyan #8fe3ff windows between frosty white shelves, layered cloudy inclusions and visible frost. One deep off-center natural cleft and a few small fractures, no VFX cracks. No long crystal needles, no purple minerals. Broad cyan and frosted surfaces distinguish ice at 64px. Entire object centered at about 85% max extent with clear transparent margin all around, no clipping. No lettering, text, logos, border, frame, UI, signature, watermark.
```

### rock_crystal_1.png

```text
Create ONE final production game sprite rock_crystal_1.png. Single complete isolated purple-crystal asteroid, square canvas with genuinely TRANSPARENT real-alpha background, no backdrop, no ground/cast shadow, no glow haze outside object, no detached particles. Hard-SF concept-art digital PAINTING: realistic richly painted rough charcoal geology and translucent mineral surfaces, intricate material texture and restrained saturation except ore, NOT vector, low-poly, anime, toy or cheap CGI. Strong cool blue-white illumination from UPPER LEFT; lower right deep shadow, thin faint purple rim on rock. Compact approximately ROUND dark cratered asteroid base with MANY stout purple crystal prisms protruding from it, all tips together form a roughly circular irregular silhouette width/height near 1:1 and below 1.2. Arrange clusters of short thick crystals at upper left, center right and lower rim rather than one tall spire. Purple #e58bff translucent crystals visibly glow FROM INSIDE with pale magenta cores and darker violet outer facets, glow confined within crystals and faint reflected purple on adjacent rock only. The material reads purple crystal ore immediately at 64px; substantial dark natural rocky core remains visible. Crystals are organic minerals, not mesh polygons, no lava or lightning VFX. Center entire object at about 85% maximum extent with every tip fully inside generous transparent margin. No letters, text, logos, UI, border, frame, watermark or signature.
```

### rock_crystal_2.png

```text
Create ONE final production game sprite rock_crystal_2.png, a distinctive SECOND purple-crystal asteroid. Square canvas genuinely TRANSPARENT real alpha, no backdrop, no cast shadow, no halo/glow spill beyond silhouette, no detached fragments. Hard-SF concept-art digital PAINTING with tactile natural charcoal stone and realistic mineral detail; restrained saturation except glowing ore. NOT vector, low-poly, anime, toy, or cheap CGI. Strong cool blue-white key light from UPPER LEFT, deep lower-right shadows, subtle thin violet rim confined to rock. A compact nearly ROUND craggy asteroid, total width/height near 1:1 never above 1.2, silhouette uneven broadly squarish-round with a chunky lower-right lobe. One prominent exposed geode cavity near center/upper-left filled with MANY thick short luminous PURPLE crystal prisms #e58bff, clusters project from top center and the left and right flanks. Crystal interiors shine pale magenta, edges darker amethyst, irregular chipped facets and internal inclusions, clearly self-illuminated from within but no bloom or particles outside. Dark pitted basalt wraps around cavity as a heavy horseshoe, NOT an actual hole through asteroid, bottom rocky mass visible. Distinct from crystals randomly scattered over a cratered ball: this variant has a clustered central geode and chunky terraced rock. Purple versus charcoal reads instantly at 64px. Center the complete object, all tips inside about 85% maximum square extent with empty transparent border. No VFX cracks, lettering, logo, frame, UI, signature or watermark.
```

### comet.png

```text
Create ONE final production game sprite comet.png. A single COMET NUCLEUS, complete isolated compact white ice-and-crystal mass, NO TAIL of any kind. Square genuinely TRANSPARENT real alpha background, no backdrop, cast shadow, halo, bloom, plume, mist, particles or orbiting fragments. Hard-SF concept-art digital PAINTING with rich realistic painted material and fine natural texture, not vector, low-poly, anime, toy or cheap CGI. Strong cool blue-white directional light from UPPER LEFT, shaded lower-right crevices and extremely thin faint violet rim confined to object. Compact broadly ROUND natural nucleus, uneven circular outline with width/height near 1:1 and always below 1.2. Dense pearly WHITE frozen ice crust and a cluster of short stout clear WHITE crystalline points fused into whole mass, frosted crystalline ridges and translucent glacial layers, only very pale cyan accents. White crystalline interiors gleam visibly more brightly and exceptionally than ordinary blue ice asteroids; a special luminous resource yet preserve sculpted material detail, no overexposure across whole form. Some dark slate blue fissures define volume lower right. No purple ore or orange. A complete centered object occupying about 85% maximum square extent with clear transparent margin all around, every point inside. No exhaust, tail, VFX, lettering, logo, border, frame, UI, watermark or signature.
```

### far.png

```text
Create ONE final production game sprite far.png: a distant enormous dark asteroid used as a subtle vanishing-point landmark. Square genuinely TRANSPARENT real alpha background, NO black backdrop, no space scene behind it, no ground, cast shadow, particles, halo or detached fragments. Hard-SF concept-art digital PAINTING, fine realistically painted pitted charcoal rock, intricate muted natural geological texture, not vector, low-poly, anime, toy or cheap CGI. One very old gigantic approximately ROUND craggy asteroid, width/height near 1:1 (below 1.2), slightly flattened top and cratered irregular boulder outline. Lighting is extremely restrained: ONLY THE UPPER-LEFT EDGE and a narrow adjacent strip receive cool blue-white key light; the entire rest of the face is in deep charcoal / blue-black shadow, still faintly readable material detail. Lower-right rim at most a barely perceptible muted violet glint, no glowing ores, no orange, no bright areas anywhere else. Rock should look far darker than normal collectible asteroids, not a fully illuminated gray rock. Strong sense of massive scale through minute craters and long erosion grooves. Complete object centered at about 85% maximum square extent, transparent margin all sides, no cropping. No lettering, logos, border, frame, labels, UI, watermark, signature. Real transparency must preserve the shadowed rock, do not key out its black surface.
```

### bg.jpg

```text
Create ONE finished landscape game background bg.jpg, composition aspect ratio 4:3, intended final resolution 2048x1536. OPAQUE full-bleed deep outer space. Hard science-fiction concept-art digital PAINTING, rich subtle realistic astronomical clouds and fine star points, same cool upper-left lighting language as realistic painted asteroid game assets, restrained navy, indigo and muted violet palette, not vector, low-poly, anime, toy, or cheap CGI. CRITICAL LAYOUT: top LEFT corner and top RIGHT corner contain the only luminous nebula wisps, softly cyan-blue on upper left, dim dusty violet on upper right. Keep all noticeably bright clouds confined to the TOP QUARTER and outer upper corners, not the top middle. A very distant faint sparse asteroid belt, tiny dark irregular pebbles dimly rimlit from upper left, gently arcs across upper quarter only. The ENTIRE CENTRAL region and LOWER TWO THIRDS must be very dark, quiet, open, near-black navy around #060818, with only extremely sparse faint tiny stars and almost imperceptible dust; this is negative space for gameplay lanes and moving sprites. No central bright star, no large stars, no starburst, no flare, no planets, no giant moon, no ship, no foreground asteroids, no beams, no game lanes, no UI, no grid. Atmospheric depth, carefully understated detailed hand-painted nebula in the upper corners but ample calm darkness from center down. No lettering, logo, borders, signature or watermark. Fill entire 4:3 image, no transparency.
```
