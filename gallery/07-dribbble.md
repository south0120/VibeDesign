# DESIGN.md — Dribbble風クリエイティブポートフォリオ

> クリエイターの作品が主役になる、洗練されたポートフォリオプラットフォームのデザインシステム。

---

## Project Overview

- **Project Name**: Shotfolio — クリエイターの作品を輝かせるポートフォリオプラットフォーム
- **Vibe**: "作品が主役。余計な装飾を排し、クリエイターのビジュアルを最大限に引き立てる上品でプレイフルな空間"
- **Target User**: 20〜40歳のUI/UXデザイナー、イラストレーター、グラフィックデザイナー

---

## Color Palette & Roles

```
Primary:      #EA4C89   （メインCTA・いいねアイコン・ブランドカラー）
Secondary:    #6E5494   （プロバッジ・プレミアム機能）
Background:   #FFFFFF   （ページ背景。作品を際立たせる白）
Surface:      #F8F7F4   （カード背景・セクション背景。温かみのあるオフホワイト）
Text:         #0D0C22   （本文テキスト。深い紺黒）
Text-muted:   #6E6D7A   （補足テキスト・メタ情報）
Accent:       #2EB67D   （成功・フォロー完了・公開済みバッジ）
Border:       #E7E7E9   （区切り線・カード枠線）
```

**コントラスト比の必須要件**
- Body text（#0D0C22 on #FFFFFF）: 17.1:1 ✅ WCAG AAA
- Text-muted（#6E6D7A on #FFFFFF）: 4.7:1 ✅ WCAG AA
- Primary（#EA4C89 on #FFFFFF）: 3.6:1 ✅ Large text AA
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Haas Grotesk", "Helvetica Neue", sans-serif
Base size:     14px
Line height:   1.65
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: SemiBold（600）、20px
  H4: Medium（500）、16px

Body: Regular（400）、14px
Small: Regular（400）、13px
Caption: Regular（400）、12px
```

---

## Component Stylings

### Button
```
Border radius:  8px
Padding:        10px 16px
Min width:      auto
Font weight:    SemiBold（600）
Font size:      14px

Primary button:
  background: #EA4C89
  color: #FFFFFF
  border-radius: 8px

Secondary button:
  background: #F8F7F4
  border: none
  color: #0D0C22
  border-radius: 8px

Hover state:
  Primary: background #D4407A
  Secondary: background #E7E7E9
```

### Card（ショット）
```
Border radius:  8px
Padding:        0px
Border:         none
Shadow:         none
Image aspect:   4:3（800×600推奨）
Image radius:   8px
Overlay:        ホバー時に半透明オーバーレイ（rgba(13,12,34,0.5)）
Overlay content: タイトル + いいね・保存アイコン
```

### Input / Form
```
Border radius:  8px
Border:         1px solid #E7E7E9
Padding:        10px 16px
Font size:      14px
Focus outline:  2px solid #EA4C89
Background:     #FFFFFF
```

### Navigation
```
Height:         64px
Background:     #FFFFFF
Border-bottom:  1px solid #E7E7E9
Logo width:     76px
Logo color:     #0D0C22
Link spacing:   24px
Active link:    font-weight 700, color #0D0C22
Inactive link:  font-weight 400, color #6E6D7A
```

---

## Layout Principles

```
Max width:        1400px
Outer padding:    64px（デスクトップ）/ 20px（モバイル）
Section spacing:  48px
Grid columns:     12
Gutter:           24px
Shot grid:        4カラム（デスクトップ）/ 3カラム（タブレット）/ 2カラム（モバイル）
Breakpoints:      768px（タブレット）/ 1024px（デスクトップ）
```

---

## Do's and Don'ts

### Do
- 作品サムネイルは4:3のアスペクト比で統一する
- ホバーインタラクションでカードに生命感を与える
- いいね（♥）アイコンにはPrimary color（#EA4C89）を使用する
- デザイナーのアバターは丸型（40px × 40px）で表示する
- グリッドレイアウトで作品を均等に配置する
- ホワイトスペースを十分に取り、作品同士の間隔を保つ

### Don't
- 作品サムネイルを歪めたりトリミングで潰したりしない
- 背景にPrimary color（#EA4C89）を全面使用しない
- ショットカードに影（box-shadow）を常時表示しない（ホバー時のみ）
- テキスト量の多いレイアウトにしない（ビジュアルファースト）
- 3種類以上のグリッドレイアウトを1ページ内で混在させない
- ユーザーネームやメタ情報を作品より目立たせない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
