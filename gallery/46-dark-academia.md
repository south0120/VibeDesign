# DESIGN.md — ダークアカデミア

> 古書・大学図書館の雰囲気を持つダークブラウンベースのデザインシステム。  
> 学術的で知的な世界観を演出するセリフ体中心のスタイル。

---

## Project Overview

- **Project Name**: Dark Academia
- **Vibe**: "古い大学図書館の書斎。革の装丁と万年筆のインク、知性と伝統が香るアカデミックな空間"
- **Target User**: 知的好奇心の強い20〜30代。文学・哲学・歴史を愛する層

---

## Color Palette & Roles

```
Primary:      #8B6914   （メインCTA・リンク・ブランドカラー。古い金箔のようなゴールド）
Secondary:    #5C6B3C   （サブアクション・タグ。深い苔色）
Background:   #1C1610   （ページ背景。古い革のような深いダークブラウン）
Surface:      #2A2318   （カード・セクション背景。やや明るいダークブラウン）
Text:         #D4C5A9   （本文テキスト。羊皮紙のようなベージュ）
Text-muted:   #9A8B72   （補足テキスト・キャプション。くすんだベージュ）
Accent:       #6B4423   （強調・バッジ。ダークレンガ色）
Border:       #3D3328   （区切り線・枠線。焦げ茶の境界線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "EB Garamond", "Noto Serif JP", serif
Font-en:       "EB Garamond", Georgia, serif
Base size:     17px
Line height:   1.8
Letter spacing: 0.03em（日本語テキストに適度な余裕）

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、19px

Body: Regular（400）、17px
Small: Regular（400）、15px
Caption: Regular（400）、13px
```

**フォント方針**
- すべてセリフ体で統一。サンセリフは使用しない
- 見出しは `EB Garamond` のイタリック体も可
- 引用文には `font-style: italic` を適用

---

## Component Stylings

### Button
```
Border radius:  4px
Padding:        14px 28px
Min width:      140px
Font weight:    Bold（700）
Font size:      16px
Font family:    "EB Garamond", serif
text-transform: none
letter-spacing: 0.05em

Primary button:
  background: #8B6914
  color: #1C1610
  border: 1px solid #8B6914
  hover: background #A07D1E, box-shadow: 0 2px 12px rgba(139,105,20,0.3)

Secondary button:
  background: transparent
  border: 1px solid #8B6914
  color: #D4C5A9
  hover: background rgba(139,105,20,0.1)
```

### Card
```
Border radius:  2px
Padding:        32px
Border:         1px solid #3D3328
Shadow:         0 4px 16px rgba(0,0,0,0.3)
Background:     #2A2318

装飾: カード上部に 2px solid #8B6914 のトップボーダーを付与可
```

### Input / Form
```
Border radius:  2px
Border:         1px solid #3D3328
Padding:        12px 16px
Font size:      17px
Font family:    "EB Garamond", serif
Background:     #2A2318
Color:          #D4C5A9
Focus outline:  2px solid #8B6914
Placeholder:    #9A8B72
```

### Navigation
```
Height:         72px
Background:     #1C1610
Border-bottom:  1px solid #3D3328
Logo width:     140px
Link spacing:   36px
Link color:     #D4C5A9
Link hover:     #8B6914
Font size:      15px
Font weight:    400
letter-spacing: 0.08em
```

---

## Layout Principles

```
Max width:        960px（読書に適した狭めのコンテンツ幅）
Outer padding:    80px（モバイルは 24px）
Section spacing:  120px（セクション間に十分な間を確保）
Grid columns:     12
Gutter:           32px
```

**レイアウト方針**
- 1カラムを基本とし、テキストの可読性を最優先
- 最大テキスト幅は 680px（長文の読みやすさのため）
- 画像は控えめに。使う場合はセピア調フィルター推奨

---

## Do's and Don'ts

### Do
- セリフ体のみで統一する
- ダークブラウン〜ゴールドのカラーパレットを厳守する
- テキスト中心のレイアウトを心がける
- 余白を十分に取り、上品な印象を維持する
- 引用ブロックにはイタリック体と左ボーダーを使用する
- 区切りには `<hr>` をシンプルに。装飾は最小限

### Don't
- サンセリフ体を混在させない
- 鮮やかな色（ネオン・蛍光色）を使わない
- 過度なアニメーションやトランジションを使わない
- 画像を大きく配置しすぎない（テキストが主役）
- グラデーション背景を使用しない
- コントラスト比 4.5:1 を下回るテキストを置かない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
