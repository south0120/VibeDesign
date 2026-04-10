# DESIGN.md — 設計図・ブループリント

> 技術文書風の青写真。方眼紙の上に白い線で描かれた精密な設計図の世界観。

---

## Project Overview

- **Project Name**: Blueprint Technical
- **Vibe**: "製図室のブループリント。白線で描かれた精密な設計図が青い紙に浮かび上がる"
- **Target User**: エンジニア、建築事務所、技術ドキュメントサイト、SaaS開発ツール

---

## Color Palette & Roles

```
Primary:      #FFFFFF   （メインCTA・リンク。白い線＝設計線）
Secondary:    #87CEEB   （サブアクション・タグ。薄い青白い線）
Background:   #003366   （ページ背景。ブループリントの深い青）
Surface:      #004080   （カード・セクション背景。やや明るい青）
Text:         #FFFFFF   （本文テキスト。白い設計線）
Text-muted:   rgba(255,255,255,0.6)  （補足テキスト・キャプション。薄い白線）
Accent:       #FFD700   （強調・警告・バッジ。注記マーカーの黄色）
Border:       rgba(255,255,255,0.2)  （区切り線・枠線。方眼のグリッド線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #FFFFFF on #003366 = 12.1:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Courier New", "Source Code Pro", monospace
Font-en:       "Courier New", "Source Code Pro", monospace
Base size:     15px（モノスペースは少し小さめが読みやすい）
Line height:   1.7
Letter spacing: 0.04em

Heading weights:
  H1: Bold（700）、28px、text-transform: uppercase
  H2: Bold（700）、22px、text-transform: uppercase
  H3: Regular（400）、18px、text-transform: uppercase
  H4: Regular（400）、16px

Body: Regular（400）、15px
Small: Regular（400）、13px
Caption: Regular（400）、11px、text-transform: uppercase、letter-spacing: 0.08em
```

**ブループリント・タイポグラフィルール**
- モノスペースフォントを全面的に使用（設計図・技術文書の雰囲気）
- 見出しはuppercase
- 数値は常に単位付き（px, mm, kg など）で表記
- セクション番号は「§1.0」「§2.1」のように小数点付きで表記
- 座標・寸法表記: (x: 120, y: 340) のような技術的フォーマット

---

## Component Stylings

### Button
```
Border radius:  0px（角張った製図スタイル）
Padding:        10px 24px
Min width:      120px
Font weight:    Bold（700）
Font size:      13px
text-transform: uppercase
letter-spacing: 0.1em
font-family:    "Courier New", monospace

Primary button:
  background: transparent
  color: #FFFFFF
  border: 1.5px solid #FFFFFF
  （白枠線のボタン＝設計図のラベル）

Secondary button:
  background: transparent
  border: 1px dashed rgba(255,255,255,0.5)
  color: rgba(255,255,255,0.7)

Accent button:
  background: transparent
  border: 1.5px solid #FFD700
  color: #FFD700

Hover:
  background: rgba(255,255,255,0.1)、transition: 0.2s
```

### Card
```
Border radius:  0px
Padding:        24px
Border:         1px solid rgba(255,255,255,0.2)
Shadow:         none（フラット。ブループリントに影はない）
Background:     #004080

角の装飾:
  四隅に十字マーカー（+）をCSS疑似要素で配置
  content: "+"、font-size: 10px、color: rgba(255,255,255,0.3)
```

### Input / Form
```
Border radius:  0px
Border:         1px solid rgba(255,255,255,0.3)
Padding:        10px 14px
Font size:      15px
Font family:    "Courier New", monospace
Background:     rgba(255,255,255,0.05)
Color:          #FFFFFF
Focus outline:  1px solid #FFD700
Placeholder:    rgba(255,255,255,0.3)
```

### Navigation
```
Height:         56px
Background:     #003366
Border-bottom:  1px solid rgba(255,255,255,0.15)
Logo width:     100px
Link spacing:   32px
Link style:     font-size: 12px, uppercase, letter-spacing: 0.1em, monospace
Active link:    color: #FFD700、border-bottom: 1px solid #FFD700
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    60px（モバイルは 20px）
Section spacing:  72px
Grid columns:     12
Gutter:           24px

方眼紙背景:
  background-image:
    linear-gradient(rgba(255,255,255,0.05) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.05) 1px, transparent 1px)
  background-size: 20px 20px（方眼のサイズ）

セクション装飾:
  - セクションタイトルの横に寸法線（├── SECTION 1.0 ──┤）を CSS で表現
  - 番号は §1.0, §2.0 形式
  - 要素間の距離をコメント風に表記（例: /* margin: 24px */ を装飾として見せる）

座標マーカー:
  ページの端に座標軸（X, Y）を薄く表示する装飾
```

---

## Do's and Don'ts

### Do
- モノスペースフォントを全面的に使う
- 方眼紙グリッドを背景に薄く表示する
- 白い線・枠線で要素を区切る（影ではなく線）
- 技術的な数値表記（単位付き、座標形式）を積極的に使う
- 四隅の十字マーカーやスケール表記など、設計図らしい装飾を入れる
- ダッシュ線（dashed）を補助線として活用する

### Don't
- 丸みのあるデザイン（border-radius）を使わない
- ドロップシャドウを使わない（ブループリントは平面）
- 青系以外の背景色を使わない
- 装飾フォント・手書きフォントを使わない
- グラデーション背景を使わない
- 画像を多用しない（図面・ダイアグラムは可）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
