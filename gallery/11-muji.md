# DESIGN.md — 無印良品風デザインシステム

> 究極のミニマリズム。素材感と余白が語るデザイン。

---

## Project Overview

- **Project Name**: MUJI Minimal — 素材と余白のデザインシステム
- **Vibe**: "何も足さない、何も引かない。素材そのものの美しさと、呼吸するような余白が心地よさを生む"
- **Target User**: 30〜50代のシンプルな暮らしを好む、品質に敏感な消費者

---

## Color Palette & Roles

```
Primary:      #B52A2A   （メインCTA・ブランドアクセント。無印の赤）
Secondary:    #8B7355   （サブアクション・タグ。ナチュラルブラウン）
Background:   #FFFFFF   （ページ背景。清潔な白）
Surface:      #F5F1EB   （カード・セクション背景。生成りのようなウォームグレー）
Text:         #333333   （本文テキスト。柔らかい黒）
Text-muted:   #999999   （補足テキスト・キャプション）
Accent:       #D4A574   （強調・バッジ。木目を思わせるベージュ）
Border:       #E5E0D8   （区切り線・枠線。素材感のある薄いベージュ）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #333333 on #FFFFFF = 12.63:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", "Hiragino Kaku Gothic ProN", sans-serif
Font-en:       "Inter", "Helvetica Neue", sans-serif
Base size:     15px
Line height:   1.9
Letter spacing: 0.04em（日本語の読みやすさを重視した広めの字間）

Heading weights:
  H1: Medium（500）、28px
  H2: Medium（500）、22px
  H3: Regular（400）、18px
  H4: Regular（400）、16px

Body: Regular（400）、15px
Small: Regular（400）、13px
Caption: Light（300）、11px
```

**デザイン意図**: 無印良品の世界観に合わせ、見出しもBoldではなくMedium〜Regularを使用。文字の太さで主張せず、余白とサイズの差で階層を表現する。

---

## Component Stylings

### Button
```
Border radius:  2px（ほぼ角張った、素朴な印象）
Padding:        14px 32px
Min width:      140px
Font weight:    Regular（400）
Font size:      14px
Letter spacing: 0.08em

Primary button:
  background: #B52A2A
  color: #FFFFFF
  border: none
  transition: opacity 0.2s ease

Secondary button:
  background: transparent
  border: 1px solid #333333
  color: #333333

Tertiary button:
  background: transparent
  border: none
  color: #333333
  text-decoration: underline
  text-underline-offset: 4px
```

### Card
```
Border radius:  0px（角を丸めない。素材感を大切にする）
Padding:        32px
Border:         none
Shadow:         none（影を使わず、背景色の差で分離する）
Background:     Surface color (#F5F1EB)
```

### Input / Form
```
Border radius:  0px
Border:         none
Border-bottom:  1px solid #E5E0D8
Padding:        12px 0px
Font size:      15px
Focus outline:  border-bottom 2px solid #333333
Background:     transparent
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Logo width:     80px（ロゴは小さく控えめに）
Link spacing:   40px
Font size:      13px
Font weight:    Regular（400）
Letter spacing: 0.06em
Border-bottom:  1px solid #E5E0D8
```

### Image
```
Border radius:  0px
Object-fit:     cover
Aspect ratio:   4:3 または 1:1（商品写真は正方形推奨）
Filter:         none（写真の加工は最小限に）
```

---

## Layout Principles

```
Max width:        960px（コンテンツ幅を狭めて余白を最大化）
Outer padding:    120px（左右余白を贅沢に取る。モバイルは 24px）
Section spacing:  120px（セクション間は大きく呼吸させる）
Grid columns:     12
Gutter:           40px（カラム間もゆったり）
```

**余白の哲学**
- 余白は「何もない場所」ではなく「空気が流れる場所」として扱う
- コンテンツ量を減らし、一画面に置く情報は最小限にする
- 写真と写真の間、テキストとテキストの間に十分な間隔を確保する

---

## Do's and Don'ts

### Do
- 余白を惜しまず使う。コンテンツの周囲に最低 40px の余白を確保する
- 色数は最小限に。Primary の赤は CTA のみに使い、画面全体の 5% 以下に抑える
- 写真は自然光で撮影されたような、素材感が伝わるものを使う
- テキストは短く、必要最低限の言葉で伝える
- フォームは下線スタイルを基本とし、枠線で囲まない

### Don't
- グラデーション、ドロップシャドウ、角丸を使わない
- 太字（Bold 700）を多用しない。Medium（500）までに留める
- 装飾的なアイコンやイラストを使わない
- 背景に模様やテクスチャを敷かない
- アニメーションは最小限に。派手なトランジションは世界観を壊す
- 色付きの背景セクションを連続させない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
