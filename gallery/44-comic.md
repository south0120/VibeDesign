# DESIGN.md — コミック・マンガ風

> 吹き出し、集中線、ハーフトーン。POW! BAM! CRASH! ポップで元気なコミックの世界。

---

## Project Overview

- **Project Name**: Comic Pop
- **Vibe**: "アメコミのページから飛び出したような大胆でポップなデザイン。読者をワクワクさせる"
- **Target User**: エンタメサイト、ゲーム関連、子ども向けサービス、イベントLP

---

## Color Palette & Roles

```
Primary:      #FF1744   （メインCTA・リンク。コミックの赤。POW!の爆発色）
Secondary:    #FFAB00   （サブアクション・タグ。吹き出しのアクセント黄色）
Background:   #FFF9C4   （ページ背景。少しくすんだコミック用紙の黄色）
Surface:      #FFFFFF   （カード・セクション背景。吹き出しの白）
Text:         #1A1A1A   （本文テキスト。コミックの黒インク）
Text-muted:   #555555   （補足テキスト・キャプション）
Accent:       #2979FF   （強調・バッジ。ヒーローの青）
Border:       #1A1A1A   （区切り線・枠線。太い黒インクのアウトライン）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #1A1A1A on #FFF9C4 = 14.8:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Bangers", "Comic Neue", cursive
Font-en:       "Bangers", "Comic Neue", cursive
Base size:     16px
Line height:   1.6
Letter spacing: 0.04em

Heading weights:
  H1: Regular（400 ※Bangersは1ウェイト）、42px、text-transform: uppercase
  H2: Regular（400）、32px、text-transform: uppercase
  H3: Regular（400）、24px
  H4: Regular（400）、20px

Body: "Comic Neue", Regular（400）、16px（本文はBangersではなく可読性重視）
Small: "Comic Neue", Regular（400）、14px
Caption: "Comic Neue", Bold（700）、12px、text-transform: uppercase
```

**コミック・タイポグラフィルール**
- 見出しは「Bangers」で大文字。インパクト重視
- 本文は「Comic Neue」で可読性を確保（Comic Sansの上位互換）
- 効果音テキスト（POW! BAM!）は Bangers + 大サイズ + 回転 + 色付き
- テキストに -webkit-text-stroke: 1px #1A1A1A を適用するとインク感UP

---

## Component Stylings

### Button
```
Border radius:  8px
Padding:        14px 28px
Min width:      140px
Font weight:    Regular（400 ※Bangers使用）
Font size:      18px
Font family:    "Bangers", cursive
text-transform: uppercase
letter-spacing: 0.06em

Primary button:
  background: #FF1744
  color: #FFFFFF
  border: 3px solid #1A1A1A
  box-shadow: 4px 4px 0px #1A1A1A（オフセットシャドウ）
  -webkit-text-stroke: 0.5px #1A1A1A

Secondary button:
  background: #FFFFFF
  border: 3px solid #1A1A1A
  color: #1A1A1A
  box-shadow: 4px 4px 0px #1A1A1A

Accent button:
  background: #2979FF
  color: #FFFFFF
  border: 3px solid #1A1A1A
  box-shadow: 4px 4px 0px #1A1A1A

Hover:
  transform: translate(2px, 2px)
  box-shadow: 2px 2px 0px #1A1A1A
  transition: all 0.1s ease（キビキビした動き）

Active:
  transform: translate(4px, 4px)
  box-shadow: 0px 0px 0px #1A1A1A
```

### Card
```
Border radius:  8px
Padding:        24px
Border:         3px solid #1A1A1A（太いアウトライン！）
Shadow:         6px 6px 0px #1A1A1A（オフセットシャドウ）
Background:     #FFFFFF

ホバー時:
  transform: translate(-2px, -2px)
  box-shadow: 8px 8px 0px #1A1A1A
  transition: all 0.15s ease

吹き出しカード:
  三角形の尻尾をCSS疑似要素で追加
  ::after で border trick を使って吹き出し形状にする
```

### Input / Form
```
Border radius:  6px
Border:         3px solid #1A1A1A
Padding:        12px 16px
Font size:      16px
Font family:    "Comic Neue", cursive
Background:     #FFFFFF
Color:          #1A1A1A
Focus outline:  none
Focus border:   3px solid #2979FF
Focus shadow:   4px 4px 0px #2979FF
Placeholder:    #999999
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Border-bottom:  3px solid #1A1A1A
Logo width:     130px（コミックロゴ風）
Link spacing:   28px
Link style:     font-family: "Bangers", font-size: 16px, uppercase
Active link:    color: #FF1744, text-decoration: underline wavy
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    60px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px

コミック演出:
  - ハーフトーンドット背景:
    radial-gradient(circle, #1A1A1A 1px, transparent 1px)
    background-size: 8px 8px、opacity: 0.05
  - 集中線: セクションヒーロー部分にCSS放射状グラデーションで集中線
  - パネル風レイアウト: グリッドで漫画のコマ割り風に配置
  - 傾き: 重要な要素に transform: rotate(-2deg〜2deg) で手描き感

効果音テキスト装飾:
  font-size: 64px〜120px
  font-family: "Bangers"
  color: #FF1744 or #FFAB00
  -webkit-text-stroke: 3px #1A1A1A
  transform: rotate(-8deg)
  text-shadow: 4px 4px 0 #1A1A1A
```

---

## Do's and Don'ts

### Do
- 太い黒アウトライン（3px border）をすべての要素に使う
- オフセットシャドウ（box-shadow: Xpx Ypx 0px）でポップな立体感を出す
- ハーフトーンドットを背景テクスチャとして使う
- 効果音テキスト（POW! BAM!）を装飾要素として配置する
- 吹き出し型のカード・ツールチップを活用する
- ホバーアニメーションはキビキビと短く（0.1〜0.15s）

### Don't
- ボーダーなし・影なしのフラットデザインにしない
- 細い線（1px border）を使わない（最低2px、推奨3px）
- 落ち着いたトーン・ミニマルデザインにしない
- グラデーションをメインスタイルにしない（フラットカラー）
- blur シャドウ（box-shadow の blur 値）を使わない（常に 0px blur）
- 文字を小さくしすぎない（コミックは大きく太く！）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
