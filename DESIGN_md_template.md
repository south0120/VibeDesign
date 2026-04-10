# DESIGN.md — 最小テンプレート

> このファイルを `DESIGN.md` という名前でプロジェクトのルートに置いてください。  
> Claude Code が自動で読み込みます。  
> `[ ]` の部分を自分のプロジェクト用に書き換えてください。

---

## Project Overview

- **Project Name**: [プロジェクト名]
- **Vibe**: [世界観を1文で。例: "クリーンでプロフェッショナル。信頼と安心を伝える"]
- **Target User**: [想定ユーザー。例: "30代の中小企業経営者"]

---

## Color Palette & Roles

```
Primary:      #[HEXコード]   （メインCTA・リンク・ブランドカラー）
Secondary:    #[HEXコード]   （サブアクション・タグ）
Background:   #[HEXコード]   （ページ背景。通常は白 #FFFFFF）
Surface:      #[HEXコード]   （カード・セクション背景。薄いグレー推奨）
Text:         #[HEXコード]   （本文テキスト。通常は #1A1A1A 〜 #333333）
Text-muted:   #[HEXコード]   （補足テキスト・キャプション）
Accent:       #[HEXコード]   （強調・警告・バッジ）
Border:       #[HEXコード]   （区切り線・枠線。薄いグレー推奨）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

**わからない場合のデフォルト値**
```
Primary:      #1A73E8
Secondary:    #34A853
Background:   #FFFFFF
Surface:      #F8F9FA
Text:         #202124
Text-muted:   #5F6368
Accent:       #EA4335
Border:       #DADCE0
```

---

## Typography Rules

```
Font:          [フォント名。例: "Noto Sans JP"]
Font-en:       [英数字フォント。例: "Inter"]（なければ上と同じ）
Base size:     [px。例: 16px]
Line height:   [倍率。例: 1.75]
Letter spacing:[em。例: 0.02em]（日本語は 0〜0.05em 推奨）

Heading weights:
  H1: Bold（700）、[px。例: 32px]
  H2: Bold（700）、[px。例: 24px]
  H3: SemiBold（600）、[px。例: 20px]
  H4: SemiBold（600）、[px。例: 18px]

Body: Regular（400）、Base sizeと同じ
Small: Regular（400）、[px。例: 14px]
Caption: Regular（400）、[px。例: 12px]
```

**わからない場合のデフォルト値**
```
Font: "Noto Sans JP", sans-serif
Base size: 16px
Line height: 1.75
Letter spacing: 0.02em
H1: Bold 32px / H2: Bold 24px / H3: SemiBold 20px
```

---

## Component Stylings

### Button
```
Border radius:  [px。例: 8px]
Padding:        [例: 12px 24px]（上下 左右）
Min width:      [px。例: 120px]
Font weight:    Bold（700）
Font size:      [px。例: 16px]

Primary button:
  background: Primary color
  color: #FFFFFF

Secondary button:
  background: transparent
  border: 1px solid Primary color
  color: Primary color
```

### Card
```
Border radius:  [px。例: 12px]
Padding:        [例: 24px]
Border:         1px solid Border color
Shadow:         [例: 0 2px 8px rgba(0,0,0,0.08)]（使う場合のみ）
```

### Input / Form
```
Border radius:  [px。例: 4px]
Border:         1px solid Border color
Padding:        [例: 10px 14px]
Font size:      Base size と同じ
Focus outline:  2px solid Primary color
```

### Navigation
```
Height:         [px。例: 64px]
Background:     [例: Background color または白]
Logo width:     [px。例: 120px]
Link spacing:   [例: 32px]（リンク間の余白）
```

---

## Layout Principles

```
Max width:        [px。例: 1200px]（コンテンツの最大幅）
Outer padding:    [px。例: 80px]（左右余白。モバイルは 24px）
Section spacing:  [px。例: 96px]（セクション間の縦余白）
Grid columns:     12
Gutter:           [px。例: 32px]（カラム間の余白）
```

---

## Do's and Don'ts

### Do
- カラーパレット以外の色を使わない
- フォントは上記2種類のみ使う
- ボタンはComponent Stylingsの定義通りに作る
- 画像にはalt属性を必ず付ける

### Don't
- グラデーション背景を多用しない
- フォントを3種類以上使わない
- コントラスト比 4.5:1 を下回るテキストを置かない
- 意味なく大量のアニメーションを使わない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
