# DESIGN.md — レトロゲーム・ピクセル

---

## Project Overview

- **Project Name**: レトロゲーム・ピクセル — 8bit の世界
- **Vibe**: "ファミコン・ゲームボーイ風。限られたパレットとピクセルが生む懐かしい世界観"
- **Target User**: ゲーム関連サービス、レトロカルチャー、ファンサイト

---

## Color Palette & Roles

```
Primary:      #8BAC0F   （メインCTA・ゲームボーイグリーン）
Secondary:    #306230   （サブ・ダークグリーン）
Background:   #0F380F   （ページ背景・最も暗いグリーン）
Surface:      #306230   （カード背景・中間グリーン）
Text:         #9BBC0F   （本文テキスト・明るいグリーン）
Text-muted:   #306230   （補足テキスト）
Accent:       #E0F8CF   （最も明るいグリーン）
Border:       #0F380F   （ボーダー）
```

---

## Typography Rules

```
Font:          "Press Start 2P", "DotGothic16", monospace
Base size:     14px
Line height:   2.0（ピクセルフォントは行間広め）
Letter spacing: 0.05em

Heading weights:
  H1: Regular（400）、28px
  H2: Regular（400）、20px
  H3: Regular（400）、16px
Body: Regular（400）、14px
※ピクセルフォントはウェイト1種類のみ
```

---

## Component Stylings

### Button
```
Border radius:  0px（角ばり徹底）
Padding:        12px 24px
Border:         4px solid #9BBC0F
Primary: background #8BAC0F, color #0F380F
image-rendering: pixelated
```

### Card
```
Border radius:  0px
Padding:        16px
Border:         4px solid #306230
Background:     #0F380F
```

### Navigation
```
Height:         48px
Background:     #0F380F
Border bottom:  4px solid #306230
```

---

## Layout Principles

```
Max width:        800px（小さめ）
Section spacing:  48px
Grid:             シンプルな1-2カラム
image-rendering:  pixelated（全画像）
```

---

## Do's and Don'ts

### Do
- 4色パレットを厳守（ゲームボーイ準拠）
- border-radius: 0px を徹底
- image-rendering: pixelated を全画像に適用

### Don't
- グラデーションを使わない
- 滑らかなフォントを使わない
- 4色以上の色を使わない

---

*Design Style: Retro Game Pixel — 2026-04-10*
