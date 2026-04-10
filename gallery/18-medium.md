# DESIGN.md — Medium風デザインシステム

> 読みやすさを最優先としたパブリッシングプラットフォーム向けデザインシステム

---

## Project Overview

- **Project Name**: ReadFlow — 記事投稿・閲覧プラットフォーム
- **Vibe**: "文章が主役。装飾を削ぎ落とし、一字一句に集中できる、知的で穏やかな読書体験"
- **Target User**: ライター・ブロガー・知識共有に関心のある20〜40代のプロフェッショナル

---

## Color Palette & Roles

```
Primary:      #1A8917   （メインCTA・フォローボタン・ブランドカラー）
Secondary:    #6B6B6B   （サブアクション・タグ）
Background:   #FFFFFF   （ページ背景）
Surface:      #F7F4ED   （カード・サイドバー背景・温かみのあるベージュ）
Text:         #242424   （本文テキスト）
Text-muted:   #757575   （補足テキスト・日付・著者名）
Accent:       #E6B800   （スター・お気に入り・メンバーシップバッジ）
Border:       #E6E6E6   （区切り線・枠線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA） — #242424 on #FFFFFF = 15.1:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Serif JP", serif（記事本文）
Font-en:       "Georgia", "Charter", serif
UI-Font:       "Noto Sans JP", sans-serif（ナビ・ボタン・UI部品）
UI-Font-en:    "Inter", sans-serif
Base size:     18px（読みやすさのため大きめ）
Line height:   1.8
Letter spacing: 0.02em

Heading weights:
  H1: Bold（700）、40px（記事タイトル）
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、18px
Small: Regular（400）、15px
Caption: Regular（400）、13px

記事本文はセリフ体。UIはサンセリフ体。この使い分けを徹底する。
```

---

## Component Stylings

### Button
```
Border radius:  20px（ピル型のボタン）
Padding:        8px 16px
Min width:      80px
Font weight:    Medium（500）
Font size:      14px
Font family:    UI-Font

Primary button (フォローボタン):
  background: #1A8917
  color: #FFFFFF
  border-radius: 20px
  hover: #157013

Secondary button:
  background: transparent
  border: 1px solid #242424
  color: #242424
  border-radius: 20px

Small button (タグ):
  background: #F2F2F2
  color: #242424
  border-radius: 16px
  padding: 6px 14px
  font-size: 13px
```

### Card（記事カード）
```
Border radius:  0px
Padding:        24px 0px
Background:     transparent
Border:         none
Border-bottom:  1px solid #E6E6E6
Layout:         左にテキスト、右にサムネイル

Title font:     "Noto Serif JP", Bold, 20px
Excerpt font:   "Noto Serif JP", Regular, 16px, Text-muted
Meta font:      UI-Font, 13px, Text-muted
Thumbnail:      width 112px, height 112px, object-fit cover
```

### Input / Form
```
Border radius:  4px
Border:         1px solid #E6E6E6
Background:     #FFFFFF
Padding:        10px 14px
Font size:      16px
Focus outline:  2px solid #1A8917
```

### Navigation
```
Height:         64px
Background:     #FFFFFF
Border-bottom:  1px solid #E6E6E6
Logo width:     110px
Link spacing:   24px
Link font:      UI-Font, 14px
Link color:     #757575
Link hover:     #242424
```

---

## Layout Principles

```
Max width:        680px（記事本文の最大幅。読みやすさ最優先）
Page max width:   1192px（トップページ・リスト表示）
Outer padding:    24px（モバイルは 20px）
Section spacing:  48px
Grid columns:     12
Gutter:           24px

1行あたりの文字数: 最大40文字（日本語）を目安にする
```

---

## Do's and Don'ts

### Do
- 記事本文の最大幅は680px以内に収める（長い行は読みにくい）
- 本文にはセリフ体を使い、UIにはサンセリフ体を使い分ける
- テキストの行間は1.8以上を確保し、ゆったりと読ませる
- 画像は記事幅いっぱいに配置し、キャプションを添える
- 区切り線は薄く、控えめに使う

### Don't
- 本文エリアにサイドバーを置かない（集中を妨げる）
- 太字を多用しない（本当に重要な箇所のみ）
- ボタンやCTAを記事本文の途中に挿入しない
- 背景にグラデーションや柄を使わない
- フォントサイズを14px以下にしない（読みやすさが最優先）
- 記事リストに過剰な装飾を加えない（シンプルなテキストリストが最適）

---

*Template version: 1.0 — 2026-04-10*
