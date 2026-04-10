# DESIGN.md — Airbnb風トラベルプラットフォーム

> 温かみのあるホスピタリティ体験を提供するトラベルプラットフォームのデザインシステム。

---

## Project Overview

- **Project Name**: Warmstay — 旅の温もりを届けるトラベルプラットフォーム
- **Vibe**: "人のぬくもりを感じる旅体験。丸みのあるUIと柔らかな写真表現で、どこか懐かしい安心感を演出する"
- **Target User**: 25〜45歳の旅行好き。体験型の宿泊やユニークな滞在先を求めるユーザー

---

## Color Palette & Roles

```
Primary:      #FF385C   （メインCTA・ブランドカラー。Airbnbの象徴的なロゼ）
Secondary:    #00A699   （サブアクション・成功状態・評価バッジ）
Background:   #FFFFFF   （ページ背景。清潔感のある白）
Surface:      #F7F7F7   （カード背景・検索バー・セクション背景）
Text:         #222222   （本文テキスト。やや柔らかい黒）
Text-muted:   #717171   （補足テキスト・日付・キャプション）
Accent:       #FFB400   （スター評価・お気に入りハイライト）
Border:       #DDDDDD   （区切り線・カード枠線）
```

**コントラスト比の必須要件**
- Body text（#222222 on #FFFFFF）: 15.4:1 ✅ WCAG AAA
- Text-muted（#717171 on #FFFFFF）: 4.8:1 ✅ WCAG AA
- Primary（#FF385C on #FFFFFF）: 3.6:1 ✅ Large text AA
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Cereal", "Noto Sans JP", sans-serif
Font-en:       "Cereal", "Inter", sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: Bold（800）、32px
  H2: Bold（700）、26px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

---

## Component Stylings

### Button
```
Border radius:  8px
Padding:        14px 24px
Min width:      auto
Font weight:    Bold（700）
Font size:      16px

Primary button:
  background: linear-gradient(to right, #E61E4D, #E31C5F, #D70466)
  color: #FFFFFF
  border-radius: 8px
  transition: transform 0.2s ease

Secondary button:
  background: transparent
  border: 1px solid #222222
  color: #222222
  border-radius: 8px

Hover state:
  Primary: transform scale(1.02), shadow 0 2px 8px rgba(0,0,0,0.12)
  Secondary: background #F7F7F7
```

### Card
```
Border radius:  12px
Padding:        0px（画像フル幅 + 下部テキスト padding 12px 0）
Border:         none
Shadow:         none（ホバー時: 0 6px 20px rgba(0,0,0,0.08)）
Image aspect:   3:2
Image radius:   12px
```

### Input / Form
```
Border radius:  32px（検索バー）/ 8px（通常フォーム）
Border:         1px solid #DDDDDD
Padding:        14px 20px
Font size:      16px
Focus outline:  2px solid #222222
Background:     #FFFFFF
```

### Navigation
```
Height:         80px
Background:     #FFFFFF
Border-bottom:  1px solid #DDDDDD
Logo width:     102px
Logo color:     #FF385C
Link spacing:   24px
Search bar:     中央配置、border-radius 40px、shadow 0 1px 2px rgba(0,0,0,0.08)
```

---

## Layout Principles

```
Max width:        1760px（リスティンググリッド）/ 1120px（コンテンツ）
Outer padding:    80px（デスクトップ）/ 24px（モバイル）
Section spacing:  64px
Grid columns:     12
Gutter:           24px
Card grid:        4カラム（デスクトップ）/ 2カラム（タブレット）/ 1カラム（モバイル）
Breakpoints:      744px（タブレット）/ 1128px（デスクトップ）
```

---

## Do's and Don'ts

### Do
- 写真を大きく使い、体験の臨場感を伝える
- 角丸（8px〜12px）を一貫して使い、柔らかい印象を保つ
- ユーザーアバターは円形（border-radius: 50%）で統一する
- 余白を十分に取り、情報が呼吸できるレイアウトにする
- レビュー・評価は★アイコン + 数値で分かりやすく表示する
- 検索体験を最優先し、検索バーを目立つ位置に配置する

### Don't
- 冷たい印象のシャープな角（border-radius: 0）を使わない
- テキストだけのページを作らない（必ずビジュアルを添える）
- Primary color（#FF385C）を背景全面に使わない（CTAとロゴのみ）
- 細すぎるフォント（weight 300以下）を本文に使わない
- 情報を詰め込みすぎず、1画面に表示するカードは最大8枚までにする
- 写真の上にコントラスト不足のテキストを直接置かない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
