# DESIGN.md — 水彩画風

> にじみ、透明感、手描きの温かみ。水彩絵の具が紙に広がるような柔らかな世界観。

---

## Project Overview

- **Project Name**: Watercolor Dreamy
- **Vibe**: "絵の具が水に溶けるような透明感。手描きの温かみと柔らかさが漂うアートな空間"
- **Target User**: アーティスト、ウェディング関連サービス、ハンドメイド作家、絵画教室

---

## Color Palette & Roles

```
Primary:      #7FB3D8   （メインCTA・リンク。空色の水彩にじみ）
Secondary:    #B8D4E3   （サブアクション・タグ。薄い水色の滲み）
Background:   #FFFEF9   （ページ背景。水彩紙のオフホワイト）
Surface:      #F7F3EE   （カード・セクション背景。クリーム色の画用紙）
Text:         #4A4A4A   （本文テキスト。墨を薄めた色）
Text-muted:   #9B9B9B   （補足テキスト・キャプション）
Accent:       #E8A87C   （強調・警告・バッジ。テラコッタの水彩）
Border:       #E0D5C7   （区切り線・枠線。画用紙の端のような自然な色）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #4A4A4A on #FFFEF9 = 7.5:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Lora", "Noto Serif JP", serif
Font-en:       "Lora", serif
Base size:     16px
Line height:   1.8（ゆったりとした行間で水彩画の余白感を演出）
Letter spacing: 0.03em

Heading weights:
  H1: Bold（700）、34px、font-style: italic（手書き感）
  H2: Bold（700）、26px
  H3: SemiBold（600）、20px
  H4: Regular（400）、18px、font-style: italic

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Light（300）、12px、font-style: italic
```

**水彩タイポグラフィルール**
- 見出しにはイタリック体を適度に使い、手書きの雰囲気を出す
- セリフフォントを基本とし、上品で柔らかい印象を保つ
- 行間はやや広め（1.8）にして「余白」を感じさせる
- ウェイトは軽め〜中程度を中心に。太すぎるフォントは避ける

---

## Component Stylings

### Button
```
Border radius:  24px（丸みを帯びたピルシェイプ）
Padding:        12px 32px
Min width:      120px
Font weight:    SemiBold（600）
Font size:      15px
letter-spacing: 0.02em

Primary button:
  background: #7FB3D8
  color: #FFFFFF
  border: none
  box-shadow: 0 2px 12px rgba(127, 179, 216, 0.3)

Secondary button:
  background: transparent
  border: 1.5px solid #7FB3D8
  color: #7FB3D8

Accent button:
  background: #E8A87C
  color: #FFFFFF
  box-shadow: 0 2px 12px rgba(232, 168, 124, 0.3)

Hover:
  opacity: 0.85、transition: 0.3s ease
```

### Card
```
Border radius:  16px
Padding:        28px
Border:         1px solid #E0D5C7
Shadow:         0 4px 20px rgba(0, 0, 0, 0.04)（ソフトな影）
Background:     #FFFFFF

水彩オプション:
  background-imageで水彩テクスチャ（opacity: 0.05〜0.1）を角に配置
  不規則な余白を演出するため、padding に微妙な差をつける
    例: padding: 28px 32px 24px 30px
```

### Input / Form
```
Border radius:  12px
Border:         1.5px solid #E0D5C7
Padding:        12px 16px
Font size:      16px
Background:     #FFFEF9
Color:          #4A4A4A
Focus outline:  2px solid #7FB3D8
Focus shadow:   0 0 0 4px rgba(127, 179, 216, 0.15)
Placeholder:    #BBBBBB（薄い鉛筆書き風）
```

### Navigation
```
Height:         68px
Background:     #FFFEF9（半透明: rgba(255, 254, 249, 0.9) + backdrop-filter: blur(10px)）
Border-bottom:  1px solid #E0D5C7
Logo width:     110px（手書きロゴ推奨）
Link spacing:   28px
Link style:     font-size: 14px, color: #4A4A4A, letter-spacing: 0.02em
Active link:    color: #7FB3D8, font-style: italic
```

---

## Layout Principles

```
Max width:        1080px（やや狭めでギャラリー的な余白を確保）
Outer padding:    80px（モバイルは 24px）
Section spacing:  100px（大きめの余白で「にじみ」の間を表現）
Grid columns:     12
Gutter:           32px

水彩背景演出:
  - ページの角や端に水彩テクスチャ画像を配置（position: absolute, opacity: 0.08）
  - セクション区切りに手描き風の波線ボーダー
  - 不規則な余白: セクションごとに padding を微妙にずらす

画像演出:
  - 画像には border-radius: 16px + ソフトシャドウ
  - マスクに水彩ブラシのSVGを使うとよりアート感UP
```

---

## Do's and Don'ts

### Do
- 水彩テクスチャを背景装飾として薄く（opacity 0.05〜0.1）使う
- ソフトなシャドウ（rgba 低め）で浮遊感を出す
- セリフフォント + イタリックで手書き感を演出する
- 余白をたっぷりとり、「にじみ」の余韻を感じさせる
- 画像にはぼかしマスクやソフトなエッジ処理を施す
- オフホワイト・クリーム系の背景色を基調にする

### Don't
- 角張ったデザイン（border-radius: 0px）を使わない
- 真っ黒（#000000）をテキストに使わない（#4A4A4A程度に留める）
- ハードなドロップシャドウを使わない
- テクスチャのopacityを0.15以上にしない（うるさくなる）
- ネオンカラーや彩度の高すぎる色を使わない
- 直線的で機械的なレイアウトに固執しない（少し遊びを入れる）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
