# DESIGN.md — クレイ・3Dソフト

> ぷにっとしたクレイ質感。丸い影。ソフトな立体感。すべてがぷにぷに。

---

## Project Overview

- **Project Name**: Clay Soft 3D
- **Vibe**: "粘土細工のようなぷにぷに感。やさしい立体感と丸みが生む心地よいソフトな世界"
- **Target User**: 子ども向けサービス、教育アプリ、ヘルスケア、フレンドリーなSaaS

---

## Color Palette & Roles

```
Primary:      #FF7675   （メインCTA・リンク。ぷにっとしたコーラルピンク）
Secondary:    #A29BFE   （サブアクション・タグ。やわらかいラベンダー）
Background:   #F8F9FA   （ページ背景。うっすらグレーのやさしい白）
Surface:      #FFFFFF   （カード・セクション背景。ぷっくり浮かんだ白）
Text:         #2D3436   （本文テキスト。柔らかいほぼ黒）
Text-muted:   #949CA6   （補足テキスト・キャプション）
Accent:       #74B9FF   （強調・バッジ。ぷるんとした水色）
Border:       transparent （ボーダーは使わない。影で浮かせる）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #2D3436 on #F8F9FA = 12.6:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Nunito", "Rounded Mplus 1c", sans-serif
Font-en:       "Nunito", sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0.02em

Heading weights:
  H1: ExtraBold（800）、34px
  H2: Bold（700）、26px
  H3: SemiBold（600）、21px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: SemiBold（600）、12px
```

**クレイ・タイポグラフィルール**
- 丸みのあるフォント（Nunito）を全面的に使用
- 日本語は「Rounded Mplus 1c」で丸ゴシックに統一
- ウェイトはSemiBold〜ExtraBoldを見出しに。ぷっくり感を強調
- 文字にも微妙な影（text-shadow）をつけると粘土に刻んだ文字感が出る
  例: text-shadow: 0 1px 2px rgba(0,0,0,0.08)

---

## Component Stylings

### Button
```
Border radius:  20px（大きめ角丸。ぷにっとしたピル型）
Padding:        14px 32px
Min width:      130px
Font weight:    Bold（700）
Font size:      16px
font-family:    "Nunito", sans-serif

Primary button:
  background: #FF7675
  color: #FFFFFF
  border: none
  box-shadow:
    0 6px 0 #E55A59,         （底面の影＝クレイの厚み）
    0 8px 20px rgba(255, 118, 117, 0.3)  （ソフトな拡散影）

Secondary button:
  background: #FFFFFF
  color: #FF7675
  border: none
  box-shadow:
    0 6px 0 #E8E8E8,
    0 8px 20px rgba(0, 0, 0, 0.06)

Accent button:
  background: #74B9FF
  color: #FFFFFF
  border: none
  box-shadow:
    0 6px 0 #5AA3E8,
    0 8px 20px rgba(116, 185, 255, 0.3)

Hover:
  transform: translateY(2px)
  box-shadow の y-offset を 4px に縮小（押し込み感）
  transition: all 0.15s ease

Active:
  transform: translateY(6px)
  box-shadow: none（完全に押し込まれた状態）
```

### Card
```
Border radius:  20px（大きめ角丸！）
Padding:        28px
Border:         none（ボーダーは使わない）
Background:     #FFFFFF

Shadow（depth shadow）:
  box-shadow:
    0 10px 0 rgba(0, 0, 0, 0.04),    （底面ハードシャドウ＝厚み感）
    0 14px 30px rgba(0, 0, 0, 0.08)   （ソフト拡散影）

ホバー時:
  transform: translateY(-4px)
  box-shadow:
    0 14px 0 rgba(0, 0, 0, 0.04),
    0 20px 40px rgba(0, 0, 0, 0.1)
  transition: all 0.25s cubic-bezier(0.34, 1.56, 0.64, 1)（ぷるんとしたバウンス）

カラーバリエーション:
  ピンクカード: background: #FFF0F0, shadow に rgba(255, 118, 117, 0.15)
  ブルーカード: background: #F0F7FF, shadow に rgba(116, 185, 255, 0.15)
  パープルカード: background: #F5F3FF, shadow に rgba(162, 155, 254, 0.15)
```

### Input / Form
```
Border radius:  16px
Border:         none
Padding:        14px 18px
Font size:      16px
Background:     #FFFFFF
Color:          #2D3436
box-shadow:
  inset 0 2px 4px rgba(0, 0, 0, 0.06),  （内側の凹み影）
  0 2px 0 rgba(0, 0, 0, 0.02)

Focus:
  box-shadow:
    inset 0 2px 4px rgba(0, 0, 0, 0.06),
    0 0 0 4px rgba(255, 118, 117, 0.2)   （ぷわっと光るフォーカスリング）
  transition: box-shadow 0.2s ease
Placeholder: #CCCCCC
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Border-bottom:  none
box-shadow:     0 4px 20px rgba(0, 0, 0, 0.06)（ふわっと浮いたナビ）
Border-radius:  0 0 20px 20px（下側だけ角丸＝ぷにっとしたタブ感）
Logo width:     120px
Link spacing:   28px
Link style:     font-size: 15px, font-weight: 600, color: #2D3436
Active link:    color: #FF7675, background: rgba(255, 118, 117, 0.1), border-radius: 12px, padding: 6px 14px
```

---

## Layout Principles

```
Max width:        1160px
Outer padding:    80px（モバイルは 24px）
Section spacing:  96px
Grid columns:     12
Gutter:           28px

クレイ演出:
  - すべての要素に大きめの角丸（16px〜24px）
  - ボーダーは使わず、影（depth shadow）で要素を浮かせる
  - depth shadow のパターン:
    1. 底面ハードシャドウ（y-offset大、blur小、opacity低）→ 厚み
    2. 拡散ソフトシャドウ（y-offset中、blur大、color tint）→ 柔らかさ
  - ホバーアニメーションに cubic-bezier(0.34, 1.56, 0.64, 1) で弾み感
  - アイコンは丸い・太い線のものを使用（Phosphor Icons, Feather 推奨）

背景装飾:
  - 背景にやわらかい円形グラデーション（blob）を複数配置
    radial-gradient(circle at 20% 30%, rgba(255,118,117,0.05) 0%, transparent 50%)
  - フローティングする3D風の球体やドーナツを装飾として配置
```

---

## Do's and Don'ts

### Do
- 大きめ角丸（16px〜24px）をすべての要素に使う
- depth shadow（底面厚み + 拡散影）でぷっくり立体感を出す
- 影のカラーにオブジェクトの色を薄くミックスする（color tint shadow）
- ホバー時にバウンスするアニメーション（cubic-bezier）を使う
- 丸くて太いアイコンセットを選ぶ
- パステル系のやさしい差し色を使う

### Don't
- 角張ったデザイン（border-radius: 0〜4px）を使わない
- ボーダー（枠線）に頼らない。影で浮かせる
- 真っ黒（#000000）を使わない（最も暗くても #2D3436）
- ハードで鋭いシャドウ（blur: 0、大きな offset）を使わない
- 細いフォントウェイト（Light, Thin）を見出しに使わない
- 直線的・シャープな装飾要素を使わない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
