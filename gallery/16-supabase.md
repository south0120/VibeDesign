# DESIGN.md — Supabase風デザインシステム

> ダークモード×グリーンアクセントのBaaSプラットフォーム向けデザインシステム

---

## Project Overview

- **Project Name**: SupaStack — オープンソースBaaSダッシュボード
- **Vibe**: "ダークな空間に浮かぶネオングリーン。開発者の夜間作業に寄り添う、技術的で洗練されたプロフェッショナル感"
- **Target User**: フルスタック開発者・スタートアップのCTO・インディーハッカー

---

## Color Palette & Roles

```
Primary:      #3ECF8E   （メインCTA・リンク・ブランドカラー）
Secondary:    #6EE7B7   （サブアクション・タグ・ホバー状態）
Background:   #1C1C1C   （ページ背景）
Surface:      #2A2A2A   （カード・セクション背景）
Text:         #EDEDED   （本文テキスト）
Text-muted:   #8F8F8F   （補足テキスト・キャプション）
Accent:       #F59E0B   （警告・バッジ・重要通知）
Border:       #3A3A3A   （区切り線・枠線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA） — #EDEDED on #1C1C1C = 12.7:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- Primary on Background: #3ECF8E on #1C1C1C = 8.2:1 ✓
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", sans-serif
Base size:     15px
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、15px
Small: Regular（400）、13px
Caption: Regular（400）、11px

コードブロック:
  Font: "JetBrains Mono", "Fira Code", monospace
  Font size: 14px
  Line height: 1.5
  Background: #232323
  Border: 1px solid #3A3A3A
  Padding: 16px
  Border radius: 8px
```

---

## Component Stylings

### Button
```
Border radius:  6px
Padding:        10px 20px
Min width:      100px
Font weight:    SemiBold（600）
Font size:      14px

Primary button:
  background: #3ECF8E
  color: #1C1C1C
  hover: #34B87A

Secondary button:
  background: transparent
  border: 1px solid #3ECF8E
  color: #3ECF8E
  hover background: rgba(62, 207, 142, 0.1)

Danger button:
  background: #EF4444
  color: #FFFFFF
```

### Card
```
Border radius:  8px
Padding:        24px
Background:     #2A2A2A
Border:         1px solid #3A3A3A
Shadow:         none（ダークモードではシャドウを控える）
Hover border:   1px solid #4A4A4A
```

### Input / Form
```
Border radius:  6px
Border:         1px solid #3A3A3A
Background:     #232323
Padding:        10px 14px
Font size:      14px
Color:          #EDEDED
Placeholder:    #5F5F5F
Focus outline:  2px solid #3ECF8E
Focus background: #2A2A2A
```

### Navigation
```
Height:         56px
Background:     #1C1C1C
Border-bottom:  1px solid #2A2A2A
Logo width:     130px
Link spacing:   24px
Link color:     #8F8F8F
Link hover:     #EDEDED
Link active:    #3ECF8E
```

### Sidebar
```
Width:          240px
Background:     #1C1C1C
Border-right:   1px solid #2A2A2A
Padding:        16px
Item padding:   8px 12px
Item radius:    6px
Active item bg: rgba(62, 207, 142, 0.1)
Active item color: #3ECF8E
```

---

## Layout Principles

```
Max width:        1280px
Outer padding:    64px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px
Sidebar layout:   固定サイドバー + スクロール可能メインエリア
```

---

## Do's and Don'ts

### Do
- ダークモードの背景はレイヤーで階層を表現する（#1C1C1C → #2A2A2A → #323232）
- グリーン（#3ECF8E）はCTAとインタラクティブ要素のみに使う
- コードブロックにはモノスペースフォントを必ず使用する
- テーブルやリストは十分な行間とパディングを確保する
- アイコンはLucide Iconsなどのラインアイコンで統一する

### Don't
- グリーンを背景色として広範囲に使わない（目が疲れる）
- ダーク背景に純白（#FFFFFF）のテキストを使わない（#EDEDEDを使う）
- シャドウを多用しない（ダークモードではボーダーで階層を表現する）
- カラフルなグラデーションを使わない（モノトーン+グリーンに徹する）
- 装飾的なアニメーションを入れない（開発者ツールは速度と効率が最優先）

---

*Template version: 1.0 — 2026-04-10*
