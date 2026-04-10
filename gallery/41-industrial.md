# DESIGN.md — インダストリアル・グランジ

> 工場・金属・錆びた鉄骨。ザラついたテクスチャと無骨な力強さが支配する世界観。

---

## Project Overview

- **Project Name**: Industrial Grunge
- **Vibe**: "鋳造所の熱気と金属の重厚感。無骨で飾らない、剥き出しの力強さ"
- **Target User**: クリエイティブスタジオ、建設・製造業、インダストリアルデザイン愛好家

---

## Color Palette & Roles

```
Primary:      #E07C24   （メインCTA・リンク・錆びたオレンジ。工場の炎を想起）
Secondary:    #8B6914   （サブアクション・タグ。真鍮・黄銅のような色味）
Background:   #1C1C1C   （ページ背景。煤けた暗黒鉄板）
Surface:      #2A2A2A   （カード・セクション背景。磨かれた鋼材）
Text:         #D4D4D4   （本文テキスト。金属の表面に刻まれた文字）
Text-muted:   #888888   （補足テキスト・キャプション。薄れた刻印）
Accent:       #C0392B   （強調・警告・バッジ。危険標識の赤）
Border:       #444444   （区切り線・枠線。溶接の継ぎ目）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #D4D4D4 on #1C1C1C = 11.3:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Oswald", "Barlow Condensed", sans-serif
Font-en:       "Oswald", "Barlow Condensed", sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: 0.05em（大文字多用のため広めに）

Heading weights:
  H1: Bold（700）、36px、text-transform: uppercase
  H2: Bold（700）、28px、text-transform: uppercase
  H3: SemiBold（600）、22px、text-transform: uppercase
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px、text-transform: uppercase、letter-spacing: 0.1em
```

**インダストリアル・タイポグラフィルール**
- 見出しはすべて大文字（uppercase）にする
- キャプション・ラベルもuppercase + letter-spacing広めでステンシル感を演出
- 本文は通常ケースで可読性を確保
- 数字はtabular figures（等幅数字）を使う

---

## Component Stylings

### Button
```
Border radius:  2px（角張ったインダストリアル感）
Padding:        14px 28px
Min width:      140px
Font weight:    Bold（700）
Font size:      14px
text-transform: uppercase
letter-spacing: 0.12em

Primary button:
  background: #E07C24
  color: #1C1C1C
  border: 2px solid #E07C24
  box-shadow: none（フラットで無骨に）

Secondary button:
  background: transparent
  border: 2px solid #D4D4D4
  color: #D4D4D4

Danger button:
  background: #C0392B
  color: #FFFFFF
  border: 2px solid #C0392B

Hover:
  全ボタン共通: background を10%明るく、transition: 0.2s
```

### Card
```
Border radius:  0px（角張り。金属板のイメージ）
Padding:        24px
Border:         1px solid #444444
Shadow:         none（フラットデザイン。影よりボーダーで区切る）
Background:     #2A2A2A

ホバー時:
  border-color: #E07C24（オレンジの光が当たるイメージ）
  transition: border-color 0.3s

テクスチャオプション:
  background-image でノイズテクスチャ（5%opacity）を重ねると金属感UP
```

### Input / Form
```
Border radius:  0px
Border:         2px solid #444444
Padding:        12px 16px
Font size:      16px
Background:     #1C1C1C
Color:          #D4D4D4
Focus outline:  2px solid #E07C24
Placeholder:    #666666
```

### Navigation
```
Height:         72px
Background:     #1C1C1C
Border-bottom:  2px solid #444444
Logo width:     140px
Link spacing:   36px
Link style:     uppercase, letter-spacing: 0.08em, font-size: 13px
Active link:    border-bottom: 2px solid #E07C24
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    80px（モバイルは 24px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px

テクスチャ背景:
  - ページ全体にノイズテクスチャ（opacity: 0.03〜0.05）を適用
  - セクション区切りに工業的な水平線（border: 1px dashed #444444）
  - 背景にかすかなグリッドパターンを敷くと工場の床感が出る

セクション装飾:
  - セクション見出しの上に黄色い警告テープ風ライン（#E07C24, 4px height）
  - 番号付きセクション: 01 / 02 / 03 のように2桁表記
```

---

## Do's and Don'ts

### Do
- 大文字（uppercase）を見出し・ラベルに積極的に使う
- ザラついたノイズテクスチャを背景に薄く重ねる
- 角張ったデザイン（border-radius: 0〜2px）を徹底する
- 太いボーダー（2px）で要素を区切る
- 数値は等幅フォントで整列させる
- モノクロ写真やデュオトーン画像を使用する

### Don't
- 丸みのあるデザイン（border-radius: 12px以上）を使わない
- パステルカラーや明るい色を差し色以外に使わない
- 華奢なセリフフォントを使わない
- ドロップシャドウを多用しない（フラットに保つ）
- 可愛い・柔らかい印象のアイコンを使わない
- テクスチャの opacity を 0.1 以上にしない（うるさくなる）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
