# DESIGN.md — Notion風 ミニマルドキュメントデザイン

---

## Project Overview

- **Project Name**: Notion風 — ミニマル コンテンツファーストデザイン
- **Vibe**: "紙のような安心感。装飾を極限まで排除し、コンテンツそのものが主役になる。温かみのあるミニマリズム"
- **Target User**: ナレッジワーカー・ライター・チームの情報管理者

---

## Color Palette & Roles

```
Primary:      #000000   （メインCTA・リンクアンダーライン・選択状態 — 純粋な黒）
Secondary:    #2EAADC   （リンク・メンション・インラインハイライト）
Background:   #FFFFFF   （ページ背景・純白）
Surface:      #F7F6F3   （サイドバー・ホバー背景・温かみのあるオフホワイト）
Text:         #37352F   （本文テキスト・ほぼ黒だが温かみのある茶系）
Text-muted:   #9B9A97   （プレースホルダー・補足テキスト）
Accent:       #EB5757   （削除・警告・重要マーカー）
Border:       #E9E9E7   （区切り線・テーブル罫線）
```

**インラインカラー（テキストハイライト用）:**
```
Highlight-yellow:   #FBF3DB
Highlight-blue:     #DDEBF1
Highlight-pink:     #F4DFEB
Highlight-green:    #DDEDEA
Highlight-orange:   #FAEBDD
Highlight-purple:   #E8DEEE
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上 — #37352F on #FFFFFF = 12.9:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", -apple-system, BlinkMacSystemFont, sans-serif
Base size:     16px
Line height:   1.75
Letter spacing: 0em（日本語のナチュラルなスペーシング）

Heading weights:
  H1: Bold（700）、40px（ページタイトル）
  H2: SemiBold（600）、30px
  H3: SemiBold（600）、24px
  H4: Medium（500）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**特記:** 見出しとの間にはemoji（アイコン）を配置可能。見出しの上には余白24px、下には8pxでリズムを作る。

---

## Component Stylings

### Button
```
Border radius:  4px
Padding:        6px 12px
Min width:      auto（テキストに合わせる）
Font weight:    Medium（500）
Font size:      14px
Transition:     background 0.1s ease

Primary button:
  background: #000000
  color: #FFFFFF
  hover: background #333333

Secondary button:
  background: transparent
  border: 1px solid #E9E9E7
  color: #37352F
  hover: background #F7F6F3

Text button:
  background: transparent
  color: #9B9A97
  hover: color #37352F, background #F7F6F3
  padding: 4px 8px
```

### Card / Block
```
Border radius:  4px
Padding:        12px
Border:         none（ボーダーレスが基本）
Shadow:         none
Background:     transparent
Hover:          background #F7F6F3（ブロック選択時）
Selected:       background #D3E5EF（選択状態・ブルー系）
```

### Input / Form
```
Border radius:  4px
Border:         none（アンダーラインなし、ボーダーレス入力）
Padding:        8px 10px
Font size:      16px
Background:     transparent
Focus outline:  none（コンテンツ入力にはフォーカス枠を表示しない）
Placeholder:    #9B9A97, font-style: italic
```

**検索バー:**
```
Background:     #F7F6F3
Border:         none
Border radius:  4px
Padding:        10px 36px（左にアイコン余白）
```

### Navigation (Sidebar)
```
Width:          260px
Background:     #F7F6F3
Logo width:     auto
Item padding:   4px 12px
Item radius:    4px
Item font-size: 14px
Active item:    background #EDEDEC, font-weight 500
Hover item:     background #EDEDEC
Section toggle: ▶ 三角アイコン、10px
Nested indent:  24px per level
```

### Toggle / Callout Block
```
Callout:
  Background:     #F7F6F3
  Border radius:  4px
  Padding:        16px 16px 16px 48px（左にアイコン余白）
  Icon size:      24px

Toggle:
  Padding:        4px 0
  Arrow:          ▶ → ▼ 回転アニメーション 0.2s
```

---

## Layout Principles

```
Max width:        900px（コンテンツの最大幅 — 読みやすさ重視の狭い幅）
Outer padding:    96px（左右均等・モバイル: 24px）
Section spacing:  8px（ブロック間は極めてタイト）
Grid columns:     自由（カラムブロックで2〜5カラム対応）
Gutter:           16px
```

**特徴的なレイアウトルール:**
- コンテンツ幅は900pxを超えない（長文の可読性を保つ）
- ブロック間のスペースは最小限（8px）で密度を保つ
- 見出し前の余白（24px）でセクション区切りを表現
- ページ全体がフラットなブロックの縦積み構造

---

## Do's and Don'ts

### Do
- テキストコンテンツを最優先にデザインする
- ホバーで初めてUIコントロール（＋、⋮メニュー等）を表示する
- ブロック間のドラッグ＆ドロップに対応する
- ページアイコンにemojiを使用して個性を出す
- テーブル・リスト・トグルなど構造化ブロックを活用する
- 「/」コマンドメニューで全機能にアクセスできるようにする

### Don't
- 装飾的な影やグラデーションを使わない
- ボタンを目立たせすぎない（UIは控えめにコンテンツが主役）
- テキストカラーに純粋な黒（#000000）を本文に使わない（温かみのある#37352Fを使う）
- コンテンツ幅を900px以上に広げない
- ボーダーを多用しない（余白で区切りを表現する）
- フォントサイズを12px未満にしない

---

*Generated: 2026-04-10 — Notion inspired design system*
