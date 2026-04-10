# DESIGN.md — パステル・カワイイ

---

## Project Overview

- **Project Name**: Pastel Kawaii
- **Vibe**: "日本のカワイイ文化をベースにした、ふわふわでやさしいパステルワールド。見ているだけで心がほっこりするデザイン"
- **Target User**: 10〜20代の女性、カワイイカルチャー好き、ファンシー雑貨・推し活ユーザー

---

## Color Palette & Roles

```
Primary:      #FF9FF3   （メインCTA・やさしいピンク）
Secondary:    #FECA57   （サブアクション・パステルイエロー）
Background:   #FFEEF8   （ページ背景。ほんのりピンクがかった白）
Surface:      #FFF4FC   （カード・セクション背景。さらに淡いピンク）
Text:         #4A3D52   （本文テキスト。やわらかいダークパープル）
Text-muted:   #8B7E96   （補足テキスト・キャプション）
Accent:       #A29BFE   （強調・パステルパープル）
Border:       #F0D9E8   （区切り線・枠線。淡いピンクのボーダー）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #4A3D52 on #FFEEF8 ≈ 7.8:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

**パステルサブカラー**
```
パステルミント:   #55EFC4
パステルブルー:   #74B9FF
パステルピーチ:   #FAB1A0
パステルラベンダー: #DDA0DD
```

---

## Typography Rules

```
Font:          "Rounded Mplus 1c", sans-serif
Font-en:       "Nunito", sans-serif（丸みのある英字フォント）
Base size:     16px
Line height:   1.8
Letter spacing: 0.03em

Heading weights:
  H1: Bold（700）、32px
  H2: Bold（700）、24px
  H3: Medium（500）、20px
  H4: Medium（500）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**ポイント**
- 丸ゴシック系フォントで統一し、やわらかい印象を保つ
- 見出しにはパステルカラーを直接使うことも可（#A29BFE, #FF9FF3）

---

## Component Stylings

### Button
```
Border radius:  24px（大きめの角丸でピルシェイプ）
Padding:        12px 28px
Min width:      120px
Font weight:    Bold（700）
Font size:      15px

Primary button:
  background: #FF9FF3
  color: #FFFFFF
  border: none
  box-shadow: 0 4px 12px rgba(255, 159, 243, 0.3)

Secondary button:
  background: #FFFFFF
  border: 2px solid #FF9FF3
  color: #FF9FF3
  box-shadow: 0 2px 8px rgba(255, 159, 243, 0.15)

Accent button:
  background: #A29BFE
  color: #FFFFFF
  border: none

Hover:
  transform: translateY(-2px)
  box-shadow intensity +30%
  transition: all 0.25s ease
```

### Card
```
Border radius:  20px（大きめの角丸）
Padding:        24px
Border:         1px solid #F0D9E8
Background:     #FFF4FC
Shadow:         0 4px 16px rgba(255, 159, 243, 0.1)

Hover時:
  transform: translateY(-4px)
  box-shadow: 0 8px 24px rgba(255, 159, 243, 0.2)
  transition: all 0.3s ease
```

### Input / Form
```
Border radius:  16px
Border:         2px solid #F0D9E8
Background:     #FFFFFF
Padding:        12px 18px
Font size:      16px
Color:          #4A3D52
Focus outline:  2px solid #FF9FF3
Focus shadow:   0 0 8px rgba(255, 159, 243, 0.3)
Placeholder:    #8B7E96
```

### Navigation
```
Height:         64px
Background:     #FFEEF8（border-bottom: 1px solid #F0D9E8）
Logo:           丸みのあるロゴ。ピンク系カラー
Link spacing:   32px
Link color:     #4A3D52
Link hover:     #FF9FF3
Font weight:    Medium（500）
```

---

## Layout Principles

```
Max width:        1080px
Outer padding:    64px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px
```

**カワイイ装飾原則**
- 角丸は最低20px以上で統一し、やわらかい印象を保つ
- シャドウはすべてパステルカラー系（rgba でピンクや紫の色味を入れる）
- アイコンは線画スタイル（stroke）で、角丸・やわらかいタッチ
- 装飾にハート・星・リボンなどのモチーフを控えめに使用可

---

## Do's and Don'ts

### Do
- 角丸を大きめ（20px+）にしてふわふわ感を出す
- シャドウにパステルカラーの色味を入れてやわらかくする
- Rounded Mplus 1cなど丸ゴシック系フォントで統一する
- ホバー時にふわっと浮くアニメーション（translateY）を付ける
- 画像にもborder-radiusを付けて角丸にする

### Don't
- 直角（border-radius: 0）のボックスを使わない
- 濃い黒（#000000）をテキストや背景に使わない
- ドロップシャドウを黒系（rgba(0,0,0,...)）で付けない
- コントラスト比 4.5:1 を下回るテキストを置かない
- フォントを角ばったゴシック体やセリフ体にしない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
