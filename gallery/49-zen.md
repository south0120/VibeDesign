# DESIGN.md — 禅・和風ミニマル

---

## Project Overview

- **Project Name**: 禅・和風ミニマル — 侘び寂びのデザイン
- **Vibe**: "日本の侘び寂び。極限まで要素を削ぎ落とし、余白と静寂が語るデザイン"
- **Target User**: 茶道・和文化、旅館、日本料理、瞑想アプリ

---

## Color Palette & Roles

```
Primary:      #8B7355   （メインCTA・枯葉色）
Secondary:    #C75C2A   （サブ・朱色）
Background:   #FAF8F5   （ページ背景・和紙色）
Surface:      #F0ECE3   （カード背景・砂色）
Text:         #3C3C3C   （本文テキスト・墨色）
Text-muted:   #9A9A9A   （補足テキスト・薄墨）
Accent:       #C75C2A   （朱色アクセント）
Border:       #D4C9B8   （枯色ボーダー）
```

---

## Typography Rules

```
Font:          "Noto Serif JP", "游明朝", serif
Base size:     16px
Line height:   2.0（和文は行間広め）
Letter spacing: 0.1em（和文のゆとり）

Heading weights:
  H1: Regular（400）、36px
  H2: Regular（400）、28px
  H3: Medium（500）、20px
Body: Regular（400）、16px
※太字は使わない。すべてRegular～Medium
```

---

## Component Stylings

### Button
```
Border radius:  2px（ほぼ直角）
Padding:        14px 40px
Font weight:    Regular（400）
Letter spacing: 0.15em
Primary: background #8B7355, color #FAF8F5
Secondary: transparent, border 1px solid #8B7355, color #8B7355
```

### Card
```
Border radius:  2px
Padding:        40px
Border:         none
Border-top:     1px solid #D4C9B8（上線のみ）
Background:     transparent
Shadow:         none
```

### Navigation
```
Height:         80px
Background:     transparent
Border:         none
Position:       absolute（背景と一体化）
```

---

## Layout Principles

```
Max width:        800px（狭く、余白を最大化）
Outer padding:    120px（デスクトップ。モバイル 32px）
Section spacing:  160px（超大余白）
Grid:             1カラム中心
```

---

## Do's and Don'ts

### Do
- 余白を限界まで広くとる
- セリフ体（明朝体）を使う
- 装飾を最小限にする（線1本で区切る）

### Don't
- Bold以上のウェイトを使わない
- 鮮やかな色を使わない
- 要素を詰め込まない

---

*Design Style: Zen Wabi-Sabi — 2026-04-10*
