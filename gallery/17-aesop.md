# DESIGN.md — Aesop風デザインシステム

> 高級感と素材感を重視したビューティ・ライフスタイルブランド向けデザインシステム

---

## Project Overview

- **Project Name**: Botanica — プレミアムスキンケアブランドサイト
- **Vibe**: "静寂の中に漂う上質さ。素材の温もりと余白が語る、洗練されたミニマリズム"
- **Target User**: 30〜50代の審美眼を持つ大人・品質重視の消費者

---

## Color Palette & Roles

```
Primary:      #252525   （メインCTA・リンク・ブランドカラー）
Secondary:    #8C7E6A   （サブアクション・タグ・カテゴリラベル）
Background:   #FFFEF2   （ページ背景・温かみのあるオフホワイト）
Surface:      #F2EDE3   （カード・セクション背景・ナチュラルトーン）
Text:         #252525   （本文テキスト）
Text-muted:   #7A7267   （補足テキスト・キャプション）
Accent:       #C4956A   （強調・ホバー・特別なハイライト）
Border:       #DDD5C8   （区切り線・枠線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA） — #252525 on #FFFEF2 = 13.5:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Serif JP", serif
Font-en:       "Cormorant Garamond", serif
Base size:     16px
Line height:   1.9
Letter spacing: 0.05em（日本語はゆとりを持たせる）

Heading weights:
  H1: Regular（400）、40px（大きく、でも軽やかに）
  H2: Regular（400）、30px
  H3: Medium（500）、22px
  H4: Medium（500）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Light（300）、12px

見出しは全てセリフ体で統一。太字は使わず、サイズと余白で階層を表現する。
```

---

## Component Stylings

### Button
```
Border radius:  0px（角張ったシャープなデザイン）
Padding:        14px 36px
Min width:      160px
Font weight:    Medium（500）
Font size:      13px
Letter spacing: 0.12em
Text transform: uppercase（英語の場合）

Primary button:
  background: #252525
  color: #FFFEF2
  hover: #3A3A3A

Secondary button:
  background: transparent
  border: 1px solid #252525
  color: #252525
  hover background: #252525
  hover color: #FFFEF2
  transition: all 0.3s ease
```

### Card
```
Border radius:  0px
Padding:        32px
Background:     #FFFEF2
Border:         none
Shadow:         none（影は使わず、余白と色で分離する）

商品カード:
  Image aspect ratio: 4:5
  Image object-fit: cover
  Title: Font-en, 18px, Regular
  Price: 14px, Text-muted
  Gap between image and text: 20px
```

### Input / Form
```
Border radius:  0px
Border:         none
Border-bottom:  1px solid #DDD5C8
Background:     transparent
Padding:        12px 0px
Font size:      16px
Font family:    "Noto Serif JP"
Focus border-bottom: 1px solid #252525
Placeholder:    #B0A898
```

### Navigation
```
Height:         80px
Background:     #FFFEF2
Logo width:     100px（ロゴは控えめに）
Link spacing:   48px
Link font:      "Cormorant Garamond", 14px
Link color:     #252525
Link letter-spacing: 0.1em
Hover:          opacity 0.6
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    120px（モバイルは 24px）
Section spacing:  120px（贅沢な余白）
Grid columns:     12
Gutter:           40px
Image-text ratio: 画像を大きく、テキストは最小限に
```

---

## Do's and Don'ts

### Do
- 余白をたっぷり取る（詰めすぎない。空間そのものがデザイン）
- 画像は高品質なものだけを使い、暖かみのあるトーンで統一する
- フォントは細く、軽やかに。太字ではなく余白とサイズで強弱をつける
- 色数は最小限に。ブラウン〜ベージュのニュアンスカラーで統一する
- ボタンは角を落とさず、シャープなラインで知性を表現する

### Don't
- ポップな色（赤・青・黄色など）を使わない
- ボタンに丸みを持たせない（border-radius: 0px を厳守）
- テキストを詰め込まない（1行の文字数は35〜40文字を目安に）
- アニメーションを派手にしない（フェードイン程度に抑える）
- ストックフォト感のある安っぽい画像を使わない
- 複数の書体を混在させない（セリフ体で統一する）

---

*Template version: 1.0 — 2026-04-10*
