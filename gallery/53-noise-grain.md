# DESIGN.md — 53. ノイズ・グレイン

> フィルム写真のようなザラつきと温かみ。デジタルなのにアナログの質感を持つ。  
> SVGフィルタによるノイズテクスチャが全体を覆い、懐かしくも洗練された印象を与える。

---

## Project Overview

- **Project Name**: Noise & Grain UI
- **Vibe**: "フィルムの粒子が呼吸するように揺らぐ、アナログ感漂うデジタル空間"
- **Target User**: 写真家、映像クリエイター、ヴィンテージ雑貨のECサイト

---

## Color Palette & Roles

```
Primary:      #1A1A1A   （メインテキスト・CTA）
Secondary:    #8B7355   （サブアクション・セピア調のアクセント）
Background:   #F5F0E8   （生成り紙のようなウォームベージュ）
Surface:      #EDE6D6   （カード背景・少し濃いベージュ）
Text:         #1A1A1A   （本文テキスト）
Text-muted:   #8C8070   （補足テキスト）
Accent:       #C4553A   （ヴィンテージレッド・限定使用）
Border:       #D4CABC   （枠線・区切り線）
```

**コントラスト比の必須要件**
- Body text（#1A1A1A on #F5F0E8）: 12.5:1 以上（WCAG AAA）
- Text-muted（#8C8070 on #F5F0E8）: 3.2:1（Large text のみ）

---

## Typography Rules

```
Font:          "Noto Serif JP", serif
Font-en:       "EB Garamond", serif
Base size:     17px
Line height:   1.85
Letter spacing: 0.04em（ゆったりした字間）

Heading weights:
  H1: Bold（700）、34px
  H2: Bold（700）、26px
  H3: SemiBold（600）、21px
  H4: Medium（500）、18px

Body: Regular（400）、17px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

---

## Component Stylings

### Button
```
Border radius:  4px（控えめな丸み）
Padding:        12px 28px
Min width:      120px
Font weight:    Bold（700）
Font size:      15px
Font family:    "EB Garamond", serif

Primary button:
  background: #1A1A1A
  color: #F5F0E8

Secondary button:
  background: transparent
  border: 1.5px solid #1A1A1A
  color: #1A1A1A
```

### Card
```
Border radius:  6px
Padding:        28px
Border:         1px solid #D4CABC
Shadow:         0 2px 12px rgba(0, 0, 0, 0.06)
Background:     #EDE6D6
※ カード上にもノイズオーバーレイを適用
```

### Input / Form
```
Border radius:  4px
Border:         1px solid #D4CABC
Padding:        10px 16px
Font size:      17px
Font family:    "EB Garamond", serif
Focus outline:  2px solid #8B7355
Background:     #F5F0E8
```

### Navigation
```
Height:         64px
Background:     #F5F0E8
Logo:           セリフ体ロゴ
Link spacing:   36px
Font family:    "EB Garamond", serif
```

---

## Layout Principles

```
Max width:        960px（読みやすさ重視のナロー幅）
Outer padding:    80px（モバイルは 24px）
Section spacing:  96px
Grid columns:     12
Gutter:           28px
```

---

## Do's and Don'ts

### Do
- ページ全体にSVGノイズフィルタオーバーレイを適用する
- 画像にもグレインエフェクトを追加する
- セリフ体で統一し、活字の雰囲気を出す
- 色はすべてウォームトーンで統一する

### Don't
- ノイズの不透明度を 0.15 以上にしない（読みにくくなる）
- 彩度の高い色を使わない
- サンセリフ体を見出しに使わない
- シャープなドロップシャドウを使わない

---

## CSS / Component Examples

### SVGノイズフィルタオーバーレイ

```css
/* HTMLに以下のSVGを非表示で配置 */
/*
<svg style="display:none">
  <filter id="grain">
    <feTurbulence type="fractalNoise" baseFrequency="0.65" numOctaves="3" stitchTiles="stitch"/>
    <feColorMatrix type="saturate" values="0"/>
  </filter>
</svg>
*/

.grain-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 9999;
  opacity: 0.08;
  filter: url(#grain);
  background: transparent;
}

/* 代替: CSS-onlyノイズ */
.grain-overlay-css {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 9999;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.7' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.08'/%3E%3C/svg%3E");
}
```

### グレインカードスタイル

```css
.grain-card {
  position: relative;
  padding: 28px;
  background: #EDE6D6;
  border: 1px solid #D4CABC;
  border-radius: 6px;
  overflow: hidden;
}

.grain-card::after {
  content: "";
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='g'%3E%3CfeTurbulence baseFrequency='0.8' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23g)' opacity='0.06'/%3E%3C/svg%3E");
  pointer-events: none;
  border-radius: 6px;
}
```

### ヴィンテージ画像エフェクト

```css
.vintage-image {
  position: relative;
  overflow: hidden;
  border-radius: 4px;
}

.vintage-image img {
  width: 100%;
  filter: sepia(0.15) contrast(1.05) brightness(0.95) saturate(0.85);
}

.vintage-image::after {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(
    ellipse at center,
    transparent 50%,
    rgba(26, 26, 26, 0.25) 100%
  );
  pointer-events: none;
}
```

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
