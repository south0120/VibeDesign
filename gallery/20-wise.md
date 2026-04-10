# DESIGN.md — Wise風 フレンドリー金融サービス

---

## Project Overview

- **Project Name**: Wise風 — フレンドリー・グローバル金融
- **Vibe**: "グリーンの安心感と親しみやすさ。複雑な国際送金をシンプルに見せる、信頼と透明性のデザイン"
- **Target User**: 海外送金・国際決済を利用するグローバルユーザー

---

## Color Palette & Roles

```
Primary:      #9FE870   （メインCTA・ブランドグリーン）
Secondary:    #163300   （セカンダリボタン・ダーク背景テキスト）
Background:   #FFFFFF   （ページ背景）
Surface:      #F2F5F3   （カード・セクション背景）
Text:         #2E2E2E   （本文テキスト）
Text-muted:   #6B7280   （補足テキスト・注記）
Accent:       #0052FF   （リンク・情報ハイライト）
Border:       #E5E7EB   （区切り線・枠線）
```

**コントラスト比**: #2E2E2E on #FFFFFF = 13.6:1 ✓

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", "Helvetica Neue", sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、48px
  H2: Bold（700）、36px
  H3: SemiBold（600）、24px
  H4: SemiBold（600）、20px

Body: Regular（400）、16px
```

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        16px 32px
Font weight:    SemiBold（600）

Primary: background #9FE870, color #163300
Secondary: transparent, border 2px solid #163300, color #163300
```

### Card
```
Border radius:  16px
Padding:        32px
Background:     #FFFFFF
Border:         1px solid #E5E7EB
Shadow:         0 2px 8px rgba(0,0,0,0.06)
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Border bottom:  1px solid #E5E7EB
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    80px（モバイルは 24px）
Section spacing:  96px
Grid columns:     12
Gutter:           32px
```

---

## Do's and Don'ts

### Do
- グリーンはCTAとポジティブな要素に使用
- 数字・金額は大きく目立たせる
- 透明性を感じさせるUI

### Don't
- グリーンをテキストカラーに使わない
- 暗すぎるデザインにしない
- 金融情報をアコーディオンに隠さない

---

*Inspired by Wise — 2026-04-10*
