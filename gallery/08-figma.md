# DESIGN.md — Figma風デザインツールプラットフォーム

> カラフルでフレンドリー、誰でも楽しくデザインできるツールのデザインシステム。

---

## Project Overview

- **Project Name**: DesignHub — みんなでつくる、カラフルなデザインコラボツール
- **Vibe**: "カラフルで遊び心があるが、プロダクトとしての信頼感も両立。多色使いでも統一感を保ち、コラボレーションの楽しさを表現する"
- **Target User**: 20〜40歳のプロダクトデザイナー、エンジニア、プロダクトマネージャー

---

## Color Palette & Roles

```
Primary:      #A259FF   （メインCTA・ブランドカラー。Figmaパープル）
Secondary:    #0ACF83   （成功・共有・コラボ状態。Figmaグリーン）
Background:   #FFFFFF   （ページ背景）
Surface:      #F5F5F5   （カード背景・セクション背景）
Text:         #1E1E1E   （本文テキスト）
Text-muted:   #8C8C8C   （補足テキスト・プレースホルダー）
Accent:       #FF7262   （警告・削除・エラー。Figmaレッド）
Border:       #E5E5E5   （区切り線・枠線）

Multi-brand colors（アクセント用途のみ）:
  Orange:     #F24E1E
  Blue:       #1ABCFE
  Green:      #0ACF83
  Red:        #FF7262
  Purple:     #A259FF
```

**コントラスト比の必須要件**
- Body text（#1E1E1E on #FFFFFF）: 16.6:1 ✅ WCAG AAA
- Text-muted（#8C8C8C on #FFFFFF）: 3.5:1 ⚠️ Large text AAのみ
- Primary（#A259FF on #FFFFFF）: 3.4:1 ✅ Large text AA
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", sans-serif
Base size:     16px
Line height:   1.5
Letter spacing: 0em（英語）/ 0.04em（日本語）

Heading weights:
  H1: Black（900）、48px
  H2: Bold（700）、36px
  H3: Bold（700）、24px
  H4: SemiBold（600）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Medium（500）、12px（大文字トラッキング 0.1em）
```

---

## Component Stylings

### Button
```
Border radius:  6px
Padding:        12px 20px
Min width:      auto
Font weight:    SemiBold（600）
Font size:      14px

Primary button:
  background: #A259FF
  color: #FFFFFF
  border-radius: 6px

Secondary button:
  background: transparent
  border: 1.5px solid #1E1E1E
  color: #1E1E1E
  border-radius: 6px

Hover state:
  Primary: background #8B3FE0
  Secondary: background #F5F5F5
```

### Card
```
Border radius:  8px
Padding:        24px
Border:         1px solid #E5E5E5
Shadow:         none（ホバー時: 0 4px 16px rgba(0,0,0,0.08)）
Background:     #FFFFFF
```

### Input / Form
```
Border radius:  6px
Border:         1.5px solid #E5E5E5
Padding:        10px 14px
Font size:      14px
Focus outline:  2px solid #A259FF
Background:     #FFFFFF
```

### Navigation
```
Height:         56px
Background:     #1E1E1E（ダークナビ）
Logo width:     55px
Logo color:     #FFFFFF
Link spacing:   32px
Link color:     #FFFFFF（opacity 0.7 → hover 1.0）
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    64px（デスクトップ）/ 24px（モバイル）
Section spacing:  80px
Grid columns:     12
Gutter:           24px
Feature grid:     3カラム（デスクトップ）/ 1カラム（モバイル）
Breakpoints:      768px（タブレット）/ 1024px（デスクトップ）
```

---

## Do's and Don'ts

### Do
- Figmaの5色（Purple, Orange, Blue, Green, Red）をアクセントとして活用する
- 各色は対応するコンセプト（コラボ=Green、作成=Purple 等）に紐付けて使用する
- イラスト・アイコンは線幅2pxのアウトラインスタイルで統一する
- インタラクティブ要素にはマイクロアニメーション（200ms ease-out）を付与する
- ダークナビ × 白コンテンツのコントラストでメリハリをつける
- コードスニペットやUIの例示にはモノスペースフォント（JetBrains Mono）を使う

### Don't
- 5色を1つのコンポーネント内に同時に使わない（最大2色まで）
- グラデーションを多用しない（ソリッドカラーが基本）
- ダークモードのナビと同じ色（#1E1E1E）をコンテンツ背景に使わない
- フォントを4種類以上使わない（本文 + 見出し + コード用の3種まで）
- イラストの線幅をコンポーネントごとに変えない
- 角丸を16px以上にしない（最大12px。ツールとしてのシャープさを保つ）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
