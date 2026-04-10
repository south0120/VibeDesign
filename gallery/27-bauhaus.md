# DESIGN.md — バウハウス

---

## Project Overview

- **Project Name**: Bauhaus Studio
- **Vibe**: "幾何学的形態と原色による機能主義デザイン。形はすべて機能に従い、装飾を排した合理的な美しさ"
- **Target User**: デザイン・建築に関心のあるプロフェッショナル、モダニズム愛好家

---

## Color Palette & Roles

```
Primary:      #E63946   （メインCTA・赤。バウハウスの原色の一つ）
Secondary:    #F4D35E   （サブアクション・黄。原色アクセント）
Background:   #FFFFFF   （ページ背景。クリーンな白）
Surface:      #F1FAEE   （カード・セクション背景。わずかに緑がかった白）
Text:         #1D3557   （本文テキスト。濃紺）
Text-muted:   #6B7F99   （補足テキスト・キャプション）
Accent:       #457B9D   （強調・青。原色の一つ）
Border:       #1D3557   （区切り線・枠線。テキストと同色で力強く）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #1D3557 on #FFFFFF ≈ 11.4:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

**バウハウス原色トリオ**
```
赤: #E63946
青: #457B9D
黄: #F4D35E
```

---

## Typography Rules

```
Font:          "DM Sans", sans-serif
Font-en:       "DM Sans", sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、40px
  H2: Bold（700）、30px
  H3: Medium（500）、24px
  H4: Medium（500）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**見出しスタイル**
- H1・H2は `text-transform: uppercase` を推奨
- 幾何学的サンセリフの特性を活かし、ウェイト差で階層を明示

---

## Component Stylings

### Button
```
Border radius:  0px（シャープなエッジ。バウハウスの直線美）
Padding:        14px 32px
Min width:      140px
Font weight:    Bold（700）
Font size:      16px
Text transform: uppercase
Letter spacing: 0.08em

Primary button:
  background: #E63946
  color: #FFFFFF
  border: none

Secondary button:
  background: transparent
  border: 3px solid #1D3557
  color: #1D3557

Tertiary（黄）:
  background: #F4D35E
  color: #1D3557
  border: none

Hover:
  opacity: 0.85
  transition: opacity 0.2s ease
```

### Card
```
Border radius:  0px
Padding:        32px
Border:         3px solid #1D3557
Background:     #FFFFFF
Shadow:         none（フラットデザイン）

装飾:
  カード上部に8px高のカラーバー（赤 #E63946 / 青 #457B9D / 黄 #F4D35E をローテーション）
```

### Input / Form
```
Border radius:  0px
Border:         2px solid #1D3557
Background:     #FFFFFF
Padding:        12px 16px
Font size:      16px
Color:          #1D3557
Focus outline:  3px solid #E63946
Placeholder:    #6B7F99
```

### Navigation
```
Height:         72px
Background:     #FFFFFF（border-bottom: 3px solid #1D3557）
Logo:           幾何学的シンボル（円＋三角＋四角の組み合わせ）
Link spacing:   40px
Link color:     #1D3557
Link hover:     #E63946
Font weight:    Bold（700）
Text transform: uppercase
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    80px（モバイルは 24px）
Section spacing:  96px
Grid columns:     12
Gutter:           32px
```

**グリッド哲学**
- 厳格な12カラムグリッドに従う
- 非対称レイアウトを意図的に使用（例: 8:4 や 5:7 の分割）
- 円・三角・四角の幾何学モチーフをデコレーションとして配置
- 余白は多めに取り、各要素が「呼吸」できるようにする

---

## Do's and Don'ts

### Do
- 赤・青・黄の原色トリオをアクセントに使う
- 幾何学的な形（円・三角・四角）をモチーフとして取り入れる
- グリッドを厳格に守り、整然としたレイアウトを保つ
- ボーダーは太め（2〜3px）でシャープに
- フォントはジオメトリック・サンセリフで統一する

### Don't
- 装飾的なフォント（スクリプト体・セリフ体）を使わない
- 角丸を使わない（すべて直角）
- グラデーションを使わない（フラットカラーのみ）
- コントラスト比 4.5:1 を下回るテキストを置かない
- 写実的なイラストやリアルな写真を大きく使わない（幾何学的・抽象的表現を優先）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
