# DESIGN.md — オーロラ・モーフィズム

---

## Project Overview

- **Project Name**: オーロラ・モーフィズム — 北欧の光
- **Vibe**: "北欧のオーロラ風グラデーション。透明感とグローが織りなす幻想的なダークUI"
- **Target User**: AI・テクノロジープロダクト、クリエイティブツール

---

## Color Palette & Roles

```
Primary:      #6EE7B7   （メインCTA・オーロラグリーン）
Secondary:    #818CF8   （サブ・オーロラパープル）
Background:   #0F172A   （ページ背景・ディープネイビー）
Surface:      rgba(15,23,42,0.8)（カード・半透明ダーク）
Text:         #E2E8F0   （本文テキスト）
Text-muted:   #64748B   （補足テキスト）
Accent:       #818CF8   （リンク・インジゴ）
Border:       rgba(110,231,183,0.2)（グリーングロー）
```

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.6
Heading weights:
  H1: Bold（700）、52px
  H2: SemiBold（600）、36px
  H3: SemiBold（600）、22px
Body: Regular（400）、16px
```

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        14px 28px
Primary: background #6EE7B7, color #0F172A
box-shadow: 0 0 24px rgba(110,231,183,0.3)（グロー）
Secondary: transparent, border 1px solid rgba(110,231,183,0.3), color #6EE7B7
```

### Card
```
Border radius:  16px
Padding:        28px
Background:     rgba(15,23,42,0.8)
backdrop-filter: blur(12px)
Border:         1px solid rgba(110,231,183,0.15)
```

### Navigation
```
Height:         60px
Background:     rgba(15,23,42,0.9)
backdrop-filter: blur(20px)
```

---

## Layout Principles

```
Max width:        1100px
Section spacing:  96px
背景にオーロラグラデーション: radial-gradient で複数色をブレンド
```

---

## Do's and Don'ts

### Do
- グロー（box-shadow with color）をアクセントに使う
- 背景にオーロラ風のradial-gradientを配置
- 半透明カード + backdrop-filter

### Don't
- 明るい背景にしない
- グローを全要素に使いすぎない
- 彩度の低い色だけにしない（鮮やかなグリーン/パープル必須）

---

*Design Style: Aurora Morphism — 2026-04-10*
