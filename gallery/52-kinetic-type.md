# DESIGN.md — 52. キネティックタイポグラフィ

> 文字そのものがUIの主役。巨大なタイポグラフィが動き、変形し、空間を支配する。  
> ビジュアル要素は最小限に抑え、テキストの力だけで世界観を構築する。

---

## Project Overview

- **Project Name**: Kinetic Typography UI
- **Vibe**: "文字が踊る。テキストだけで空間を埋め尽くす圧倒的タイポグラフィ体験"
- **Target User**: タイポグラフィ愛好家、デザインスタジオ、アート展のWebサイト

---

## Color Palette & Roles

```
Primary:      #000000   （テキスト・主要UI要素）
Secondary:    #333333   （サブテキスト・補助要素）
Background:   #FFFFFF   （純白背景でテキストを際立たせる）
Surface:      #F5F5F5   （カード背景・セクション区切り）
Text:         #000000   （本文テキスト）
Text-muted:   #999999   （補足テキスト）
Accent:       #FF0000   （強調のみに使う赤。極めて限定的に）
Border:       #E0E0E0   （区切り線）
```

**コントラスト比の必須要件**
- Body text（#000 on #FFF）: 21:1（最高コントラスト）
- Accent（#FF0000 on #FFF）: Large text のみ使用可

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Space Grotesk", sans-serif
Base size:     18px
Line height:   1.6
Letter spacing: -0.02em（タイトな字間で力強さを出す）

Heading weights:
  H1: Black（900）、200px〜（ヒーロー用。vw単位推奨）
  H2: Black（900）、72px
  H3: Bold（700）、36px
  H4: Bold（700）、24px

Body: Regular（400）、18px
Small: Light（300）、14px
Caption: Light（300）、12px

特殊:
  Display: Black（900）、clamp(80px, 15vw, 240px)（画面幅に応じて巨大化）
```

---

## Component Stylings

### Button
```
Border radius:  0px（シャープな直角）
Padding:        16px 48px
Min width:      160px
Font weight:    Black（900）
Font size:      18px
Text transform: uppercase

Primary button:
  background: #000000
  color: #FFFFFF

Secondary button:
  background: transparent
  border: 3px solid #000000
  color: #000000
```

### Card
```
Border radius:  0px
Padding:        48px
Border:         3px solid #000000
Shadow:         none（フラットに）
```

### Input / Form
```
Border radius:  0px
Border:         none / border-bottom: 3px solid #000000
Padding:        12px 0
Font size:      18px
Font weight:    Bold（700）
Focus outline:  border-bottom: 3px solid #FF0000
```

### Navigation
```
Height:         80px
Background:     #FFFFFF
Logo:           テキストロゴ（Black 900, 28px）
Link spacing:   48px
Font weight:    Bold（700）
Text transform: uppercase
```

---

## Layout Principles

```
Max width:        1440px（テキストが大きいため広め）
Outer padding:    120px（モバイルは 24px）
Section spacing:  160px（巨大テキスト間の余白を確保）
Grid columns:     12
Gutter:           24px
```

---

## Do's and Don'ts

### Do
- H1は画面幅の50%以上を占めるサイズにする
- 文字の重なり・はみ出しを恐れず使う
- `mix-blend-mode` で文字と背景を融合させる
- 文字アニメーションは1文字ずつずらして動かす

### Don't
- アイコンやイラストで画面を埋めない
- 細いフォント（Thin/Light）を見出しに使わない
- 3色以上の色を同時に使わない（白・黒・赤のみ）
- 文字サイズを均一にしない（コントラストが命）

---

## CSS / Component Examples

### mix-blend-modeテキストエフェクト

```css
.kinetic-hero {
  position: relative;
  background: #000000;
  overflow: hidden;
}

.kinetic-hero h1 {
  font-family: "Space Grotesk", sans-serif;
  font-size: clamp(80px, 15vw, 240px);
  font-weight: 900;
  color: #FFFFFF;
  mix-blend-mode: difference;
  line-height: 0.9;
  letter-spacing: -0.05em;
  text-transform: uppercase;
}

.kinetic-hero::after {
  content: "";
  position: absolute;
  width: 40vw;
  height: 40vw;
  background: #FFFFFF;
  border-radius: 50%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  mix-blend-mode: difference;
}
```

### 1文字ずつのアニメーション

```css
@keyframes slideUp {
  0% {
    transform: translateY(100%);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

.kinetic-char {
  display: inline-block;
  overflow: hidden;
}

.kinetic-char span {
  display: inline-block;
  animation: slideUp 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  animation-delay: calc(var(--char-index) * 0.04s);
  opacity: 0;
}
```

### ホバーで文字が散らばるエフェクト

```css
.scatter-text:hover span {
  display: inline-block;
  transition: transform 0.4s cubic-bezier(0.16, 1, 0.3, 1);
  transform:
    translate(
      calc((var(--random-x) - 0.5) * 60px),
      calc((var(--random-y) - 0.5) * 60px)
    )
    rotate(calc((var(--random-r) - 0.5) * 30deg));
}
```

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
