# DESIGN.md — 39: ラグジュアリー・ゴールド

> 高級ジュエリー・時計ブランド風の洗練されたデザイン。  
> 金色のアクセント、広いレタースペーシング、大文字表記が品格を演出。

---

## Project Overview

- **Project Name**: Luxury Gold UI
- **Vibe**: "パリのメゾンのショーウィンドウ。漆黒の背景に金色の文字が静かに輝く、圧倒的な品格"
- **Target User**: 高級ブランド、ジュエリー、時計、ラグジュアリーホテル、プレミアム顧客

---

## Color Palette & Roles

```
Primary:      #C9A96E   （メインCTA・リンク・ブランドカラー。アンティークゴールド）
Secondary:    #A6894A   （サブアクション・セカンダリ。ダークゴールド）
Background:   #0A0A0A   （ページ背景。漆黒）
Surface:      #141414   （カード・セクション背景。極濃グレー）
Text:         #E8DCC8   （本文テキスト。ウォームベージュ）
Text-muted:   #8B7355   （補足テキスト・キャプション。ブラウンゴールド）
Accent:       #8B7355   （強調・バッジ。ブロンズ）
Border:       #2A2520   （区切り線・枠線。ダークブラウン）
```

**ゴールドグラデーション**
```
Gold-gradient: linear-gradient(135deg, #C9A96E 0%, #E8DCC8 45%, #C9A96E 55%, #8B7355 100%)
  — テキストやボーダーに使用（background-clip: text）
```

**コントラスト比の必須要件**
- Text（#E8DCC8 on #0A0A0A）: 約12.8:1 ✓（WCAG AAA）
- Primary（#C9A96E on #0A0A0A）: 約7.4:1 ✓（WCAG AA）
- Text-muted（#8B7355 on #0A0A0A）: 約3.8:1 ✓（WCAG AA Large text）

---

## Typography Rules

```
Font:          "Cormorant Garamond", "Garamond", "Georgia", serif
Font-en:       "Cormorant Garamond", serif
Base size:     16px
Line height:   1.8
Letter spacing: 0.12em（広めのレタースペーシングが高級感の鍵）

Heading weights:
  H1: Light（300）、42px — text-transform: uppercase / letter-spacing: 0.2em
  H2: Light（300）、30px — text-transform: uppercase / letter-spacing: 0.18em
  H3: Regular（400）、22px — text-transform: uppercase / letter-spacing: 0.15em
  H4: Regular（400）、18px — letter-spacing: 0.1em

Body: Light（300）、16px — letter-spacing: 0.12em
Small: Light（300）、14px
Caption: Light（300）、12px — text-transform: uppercase / letter-spacing: 0.15em
```

**特殊ルール**
- 見出し・ボタン・ナビゲーションはすべて `text-transform: uppercase`
- font-weight は Light（300）を基本に使い、Boldは最小限に
- 文字間は常に広めに取る（最低 0.1em）
- ゴールドグラデーションテキスト: `background: gold-gradient; -webkit-background-clip: text; color: transparent`

---

## Component Stylings

### Button
```
Border radius:  0px（ラグジュアリーはシャープなエッジ）
Padding:        16px 48px（左右に十分な余白）
Min width:      200px
Font weight:    Light（300）
Font size:      13px
Font family:    "Cormorant Garamond", serif
Text transform: uppercase
Letter spacing: 0.2em

Primary button:
  background: transparent
  border: 1px solid #C9A96E
  color: #C9A96E
  hover: background: #C9A96E / color: #0A0A0A
  transition: all 0.4s ease（ゆっくりとした上品なトランジション）

Secondary button:
  background: transparent
  border: 1px solid #2A2520
  color: #8B7355
  hover: border-color: #C9A96E / color: #C9A96E

Gold filled button:
  background: linear-gradient(135deg, #C9A96E, #8B7355)
  color: #0A0A0A
  border: none
  hover: opacity: 0.9
```

### Card
```
Border radius:  0px
Padding:        40px（贅沢な余白）
Border:         1px solid #2A2520
Background:     #141414
Shadow:         none
Hover:          border-color: #C9A96E（ゴールドのボーダーに変化）
Transition:     border-color 0.4s ease
```

### Input / Form
```
Border radius:  0px
Border:         none
Border-bottom:  1px solid #2A2520（下線のみのミニマルスタイル）
Background:     transparent
Padding:        12px 0px
Font size:      16px
Font family:    "Cormorant Garamond", serif
Color:          #E8DCC8
Letter spacing: 0.1em
Placeholder:    #8B7355 / text-transform: uppercase / letter-spacing: 0.15em
Focus border:   border-bottom: 1px solid #C9A96E
Label:          font-size: 11px / text-transform: uppercase / letter-spacing: 0.2em / color: #8B7355
```

### Navigation
```
Height:         80px
Background:     #0A0A0A
Border-bottom:  1px solid #2A2520
Logo:           テキストロゴ — font-size: 24px / font-weight: 300 / letter-spacing: 0.25em / text-transform: uppercase
Logo color:     #C9A96E
Link spacing:   48px（ゆとりある間隔）
Link color:     #8B7355
Link hover:     #C9A96E
Link style:     font-size: 12px / text-transform: uppercase / letter-spacing: 0.15em
Active link:    #C9A96E / border-bottom: 1px solid #C9A96E
Transition:     color 0.3s ease
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    120px（モバイルは 32px。大胆な左右余白が高級感を生む）
Section spacing:  160px（ラグジュアリーは余白が命）
Grid columns:     12
Gutter:           48px
```

**レイアウトの原則**
```
- 余白を恐れない。空間こそがラグジュアリー
- テキストの量は最小限に。短く洗練されたコピーのみ
- 画像は大きく、フルブリードで使う
- 1セクション1メッセージの原則
- スクロールに時間がかかっても構わない。ゆったりとした体験を
```

**アニメーション**
```
- すべてのトランジションは 0.4s 以上（速いアニメーションは安っぽく見える）
- ease または cubic-bezier(0.4, 0, 0.2, 1) を使用
- スクロール連動のフェードイン: opacity 0→1, transform translateY(20px→0)
- ホバー効果は控えめに。色の変化程度に留める
```

---

## Do's and Don'ts

### Do
- 余白をたっぷり取る（セクション間は160px以上）
- テキストはすべて大文字（uppercase）+ 広いレタースペーシングにする
- フォントウェイトは Light（300）を基本に使う
- トランジションは0.4秒以上のゆっくりした速度にする
- 画像にはalt属性を必ず付ける

### Don't
- 色を3色以上使わない（黒・金・ベージュの3色で構成）
- border-radius を使わない。すべてシャープなエッジ
- 太字（Bold）を多用しない。Light が高級感を生む
- ポップアップやモーダルを多用しない
- アニメーションを0.3秒未満の速さにしない（安っぽくなる）
- フォントをサンセリフに変更しない

---

*Design: 39-luxury-gold — Luxury Gold UI*
