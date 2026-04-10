# DESIGN.md — monopo風 日本のクリエイティブエージェンシー

---

## Project Overview

- **Project Name**: monopo風 — ミニマルモノクロ・クリエイティブ
- **Vibe**: "極限まで削ぎ落としたモノクロ。タイポグラフィと余白だけで語る、日本的ミニマリズム"
- **Target User**: クリエイティブエージェンシー、デザインスタジオ、ポートフォリオサイト

---

## Color Palette & Roles

```
Primary:      #000000   （メインCTA・テキスト・ロゴ）
Secondary:    #333333   （サブアクション・ホバー状態）
Background:   #FFFFFF   （ページ背景）
Surface:      #F5F5F5   （セクション背景）
Text:         #000000   （本文テキスト）
Text-muted:   #999999   （補足テキスト・日付）
Accent:       #FF0000   （強調・限定使用）
Border:       #E0E0E0   （区切り線）
```

**コントラスト比**: #000000 on #FFFFFF = 21:1 ✓（最大値）

---

## Typography Rules

```
Font:          "Noto Sans JP", "Hiragino Sans", sans-serif
Font-en:       "Helvetica Neue", Arial, sans-serif
Base size:     15px
Line height:   1.8
Letter spacing: 0.05em

Heading weights:
  H1: Regular（400）、72px
  H2: Regular（400）、48px
  H3: Medium（500）、24px
  H4: Medium（500）、18px

Body: Regular（400）、15px
Small: Regular（400）、13px
```

---

## Component Stylings

### Button
```
Border radius:  0px（シャープエッジ）
Padding:        16px 40px
Font weight:    Regular（400）
Font size:      14px
Text transform: uppercase
Letter spacing: 0.1em

Primary: background #000000, color #FFFFFF
Secondary: transparent, border 1px solid #000000, color #000000
```

### Card
```
Border radius:  0px
Shadow:         none
Hover:          opacity 0.8
```

### Navigation
```
Height:         80px
Background:     #FFFFFF
Link size:      12px / uppercase / letter-spacing 0.15em
```

---

## Layout Principles

```
Max width:        1400px
Outer padding:    80px（モバイルは 20px）
Section spacing:  120px
Grid columns:     12
Gutter:           40px
```

---

## Do's and Don'ts

### Do
- モノクロを基本。赤は極めて限定的に
- ウェイトは軽く（Regular中心）
- 余白を大胆にとる
- 英語はすべて大文字に統一

### Don't
- Bold以上のウェイトを使わない
- 角丸を使わない
- 影（box-shadow）を使わない
- 3色以上のアクセントカラーを使わない

---

*Inspired by monopo — 2026-04-10*
