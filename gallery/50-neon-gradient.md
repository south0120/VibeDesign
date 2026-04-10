# DESIGN.md — ネオングラデーション

---

## Project Overview

- **Project Name**: ネオングラデーション — モダンSaaSトレンド
- **Vibe**: "鮮やかなグラデーションCTAとクリーンな白背景。今風のSaaSランディングページスタイル"
- **Target User**: SaaSスタートアップ、AI製品、マーケティングLP

---

## Color Palette & Roles

```
Primary:      #667EEA   （グラデーション起点: linear-gradient(135deg, #667EEA, #764BA2)）
Secondary:    #764BA2   （グラデーション終点）
Background:   #FFFFFF   （ページ背景）
Surface:      #F8F7FF   （セクション背景・薄紫）
Text:         #1A1A2E   （本文テキスト・ダークネイビー）
Text-muted:   #6B7280   （補足テキスト）
Accent:       #F093FB   （ハイライト・ピンクパープル）
Border:       #E8E4F0   （区切り線・薄紫）
```

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Base size:     17px
Line height:   1.6
Letter spacing: -0.01em

Heading weights:
  H1: Bold（700）、56px
  H2: SemiBold（600）、36px
  H3: SemiBold（600）、24px
Body: Regular（400）、17px
```

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        16px 36px
Font weight:    SemiBold（600）
Primary: background linear-gradient(135deg, #667EEA, #764BA2), color #FFFFFF
box-shadow: 0 4px 16px rgba(102,126,234,0.4)（グローシャドウ）
Hover: box-shadow 0 8px 24px rgba(102,126,234,0.5)
Secondary: background #FFFFFF, border 1px solid #E8E4F0, color #1A1A2E
```

### Card
```
Border radius:  16px
Padding:        32px
Background:     #FFFFFF
Border:         1px solid #E8E4F0
Shadow:         0 4px 20px rgba(0,0,0,0.06)
Hover:          shadow 0 8px 30px rgba(0,0,0,0.1)
```

### Navigation
```
Height:         68px
Background:     rgba(255,255,255,0.9)
backdrop-filter: blur(12px)
Border bottom:  1px solid #E8E4F0
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    64px（モバイル 24px）
Section spacing:  100px
Grid columns:     12
Gutter:           32px
```

---

## Do's and Don'ts

### Do
- CTAボタンにグラデーション + グローシャドウ
- ホバーでシャドウを拡大するインタラクション
- 白ベースにアクセントで紫グラデーション

### Don't
- グラデーションを背景全体に使いすぎない
- カードにもグラデーションを適用しない（CTAのみ）
- 彩度の低いグレー系だけにしない

---

*Design Style: Neon Gradient — 2026-04-10*
