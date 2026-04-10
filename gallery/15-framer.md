# DESIGN.md — Framer風 ボールド・クリエイティブ

---

## Project Overview

- **Project Name**: Framer風 — ボールド・クリエイティブ
- **Vibe**: "太く大胆なタイポグラフィが画面を支配する。デザインの力を最大限に見せつけるプラットフォーム"
- **Target User**: Webデザイナー、クリエイター、ノーコードビルダー

---

## Color Palette & Roles

```
Primary:      #0055FF   （メインCTA・ブランドブルー）
Secondary:    #FF0080   （セカンダリ・ホットピンク）
Background:   #000000   （ページ背景）
Surface:      #111111   （カード・セクション背景）
Text:         #FFFFFF   （本文テキスト）
Text-muted:   #666666   （補足テキスト）
Accent:       #00CCFF   （情報・ハイライト）
Border:       #222222   （区切り線）
```

**コントラスト比**: #FFFFFF on #000000 = 21:1 ✓

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Base size:     18px
Line height:   1.5
Letter spacing: -0.02em

Heading weights:
  H1: Black（900）、96px
  H2: ExtraBold（800）、64px
  H3: Bold（700）、36px
  H4: SemiBold（600）、24px

Body: Regular（400）、18px
```

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        16px 32px
Font weight:    SemiBold（600）

Primary: background #0055FF, color #FFFFFF
Secondary: transparent, border 1px solid #333333, color #FFFFFF
```

### Card
```
Border radius:  16px
Background:     #111111
Border:         1px solid #222222
Hover:          border-color #0055FF; scale(1.02)
```

### Navigation
```
Height:         64px
Background:     rgba(0, 0, 0, 0.8)
Backdrop:       blur(20px)
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    60px（モバイルは 20px）
Section spacing:  120px
Grid columns:     12
Gutter:           32px
```

---

## Do's and Don'ts

### Do
- 見出しは大胆に大きく（96px以上）
- ウェイトのコントラストを極端に（900 vs 400）
- アニメーション（スクロールトリガー）を効果的に使う

### Don't
- 小さく控えめなタイポグラフィにしない
- グレー系の中間色だけでまとめない
- 装飾的なイラストを多用しない

---

*Inspired by Framer — 2026-04-10*
