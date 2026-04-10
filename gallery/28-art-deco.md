# DESIGN.md — アール・デコ

---

## Project Overview

- **Project Name**: Art Deco Grand
- **Vibe**: "1920年代の華やかさと幾何学美を現代に。金×黒のコントラストが生み出す気品あるラグジュアリー"
- **Target User**: 高級ブランド・ラグジュアリーサービスの利用者、30〜50代の審美眼を持つ層

---

## Color Palette & Roles

```
Primary:      #D4AF37   （メインCTA・ゴールドのアクセント）
Secondary:    #8B7355   （サブアクション・アンティークゴールド）
Background:   #0D0D0D   （ページ背景。漆黒に近いブラック）
Surface:      #1A1A1A   （カード・セクション背景。やや明るいブラック）
Text:         #F5E6C8   （本文テキスト。ウォームなアイボリー）
Text-muted:   #A69070   （補足テキスト・キャプション）
Accent:       #C0392B   （強調・ルビーレッド。差し色）
Border:       #D4AF37   （区切り線・枠線。ゴールドのライン装飾）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #F5E6C8 on #0D0D0D ≈ 14.7:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Cinzel", serif
Font-en:       "Cinzel", serif
Font-body:     "Cormorant Garamond", serif（本文用。Cinzelは見出し専用としても可）
Base size:     16px
Line height:   1.8
Letter spacing: 0.06em

Heading weights:
  H1: Bold（700）、38px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**見出しスタイル**
- H1・H2に `text-transform: uppercase` と `letter-spacing: 0.12em` を適用
- ゴールド（#D4AF37）を見出しカラーとして使用可

---

## Component Stylings

### Button
```
Border radius:  0px（シャープなエッジ）
Padding:        16px 36px
Min width:      160px
Font weight:    Bold（700）
Font size:      14px
Text transform: uppercase
Letter spacing: 0.1em

Primary button:
  background: #D4AF37
  color: #0D0D0D
  border: none

Secondary button:
  background: transparent
  border: 2px solid #D4AF37
  color: #D4AF37

Accent button:
  background: #C0392B
  color: #FFFFFF
  border: none

Hover:
  background: lighten 10%
  transition: all 0.3s ease
```

### Card
```
Border radius:  0px
Padding:        32px
Border:         1px solid #D4AF37
Background:     #1A1A1A
Shadow:         none

装飾:
  border-top: 3px solid #D4AF37（金のアクセントライン）
  カード四隅に幾何学的なコーナー装飾（CSS border-image または疑似要素）
```

### Input / Form
```
Border radius:  0px
Border:         1px solid #D4AF37
Background:     #0D0D0D
Padding:        14px 18px
Font size:      16px
Color:          #F5E6C8
Focus outline:  2px solid #D4AF37
Placeholder:    #A69070
```

### Navigation
```
Height:         80px
Background:     #0D0D0D（border-bottom: 1px solid #D4AF37）
Logo:           Cinzelフォントのロゴ。ゴールドカラー
Link spacing:   40px
Link color:     #F5E6C8
Link hover:     #D4AF37
Font weight:    SemiBold（600）
Text transform: uppercase
Letter spacing: 0.08em
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    80px（モバイルは 24px）
Section spacing:  100px
Grid columns:     12
Gutter:           32px
```

**装飾原則**
- セクション区切りにゴールドのライン装飾（hr に border-color: #D4AF37）
- 幾何学的パターン（シェブロン、扇形、ジグザグ）をCSSで背景装飾に使用
- 対称的なレイアウトを基本とし、中央揃えを多用
- 余白は広めに取り、ラグジュアリーな空間を演出

---

## Do's and Don'ts

### Do
- ゴールド（#D4AF37）をライン装飾・アクセントに積極的に使う
- セリフ体（Cinzel）で気品あるタイポグラフィを実現する
- 幾何学的パターン（扇形・シェブロン・直線）を装飾に取り入れる
- 対称性と中央揃えでエレガントなレイアウトを作る
- コンテンツ周りに十分な余白を確保する

### Don't
- サンセリフ体やカジュアルなフォントを使わない
- 角丸を使わない（直線と鋭角がアール・デコの特徴）
- ネオンカラーやパステルカラーを混ぜない
- コントラスト比 4.5:1 を下回るテキストを置かない
- 金色を背景全体に使わない（アクセントと装飾に限定）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
