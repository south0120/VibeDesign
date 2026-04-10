# DESIGN.md — 38: 新聞・エディトリアル

> マルチカラムレイアウト、セリフ体、クラシックな紙面デザイン。  
> 伝統的な新聞の組版を現代のWebに落とし込んだエディトリアルスタイル。

---

## Project Overview

- **Project Name**: Newspaper Editorial UI
- **Vibe**: "格式ある朝刊の一面。伝統と信頼のセリフ体、規則正しいカラム、ドロップキャップが生む知性"
- **Target User**: メディア・出版系サービス、ニュースサイト、ジャーナリズム、読書好きのユーザー

---

## Color Palette & Roles

```
Primary:      #1A1A1A   （メインCTA・リンク・ブランドカラー。ほぼ黒）
Secondary:    #4A4A4A   （サブアクション・セカンダリテキスト）
Background:   #FBF7F0   （ページ背景。温かみのあるオフホワイト — 古い紙の色）
Surface:      #F0EBE1   （カード・セクション背景。ベージュがかったクリーム）
Text:         #1A1A1A   （本文テキスト。ほぼ黒）
Text-muted:   #6B6B6B   （補足テキスト・日付・著者名）
Accent:       #8B0000   （強調・速報バッジ・重要マーク。ダークレッド）
Border:       #1A1A1A   （区切り線・枠線。新聞の罫線は黒が基本）
```

**コントラスト比の必須要件**
- Text（#1A1A1A on #FBF7F0）: 約14.8:1 ✓（WCAG AAA）
- Text-muted（#6B6B6B on #FBF7F0）: 約4.7:1 ✓（WCAG AA）
- Accent（#8B0000 on #FBF7F0）: 約8.3:1 ✓（WCAG AAA）

---

## Typography Rules

```
Font:          "Noto Serif JP", "Georgia", serif
Font-en:       "Georgia", "Times New Roman", serif
Base size:     17px（セリフ体は少し大きめが読みやすい）
Line height:   1.9（長文の可読性を重視）
Letter spacing: 0.04em（日本語セリフ体は少し広めに）

Heading weights:
  H1: Bold（700）、36px — 新聞の大見出し風。letter-spacing: 0.08em
  H2: Bold（700）、26px
  H3: SemiBold（600）、21px
  H4: SemiBold（600）、18px — イタリック（斜体）もオプションで使用可

Body: Regular（400）、17px
Small: Regular（400）、14px
Caption: Regular（400）、12px — イタリックで写真キャプション
```

**ドロップキャップ（先頭大文字）**
```
- 記事本文の先頭1文字を大きく表示
- font-size: 3.5em（約60px）
- float: left
- line-height: 0.8
- margin: 0 8px 0 0
- font-weight: 700
- color: #1A1A1A
```

**特殊ルール**
- 日付表記は和暦・西暦どちらも可。フォーマット統一すること
- 引用部分は font-style: italic + 左にborder-left: 3px solid #8B0000
- 見出しの下には細いルール線（1px solid #1A1A1A）を引く

---

## Component Stylings

### Button
```
Border radius:  0px（新聞風はシャープな直角）
Padding:        12px 28px
Min width:      140px
Font weight:    Bold（700）
Font size:      15px
Font family:    "Noto Serif JP", serif
Text transform: none
Letter spacing: 0.05em

Primary button:
  background: #1A1A1A
  color: #FBF7F0
  border: 2px solid #1A1A1A
  hover: background: #4A4A4A

Secondary button:
  background: transparent
  border: 1px solid #1A1A1A
  color: #1A1A1A
  hover: background: #1A1A1A / color: #FBF7F0

Accent button:
  background: #8B0000
  color: #FBF7F0
  border: none
  hover: background: #A00000
```

### Card
```
Border radius:  0px
Padding:        24px
Border:         none（ラインセパレータで区切る）
Background:     transparent（背景と同化）
Border-top:     2px solid #1A1A1A（カード上部にルール線）
Border-bottom:  1px solid #1A1A1A（カード下部に細い線）
Shadow:         none
```

### Input / Form
```
Border radius:  0px
Border:         1px solid #1A1A1A
Background:     #FFFFFF
Padding:        10px 14px
Font size:      16px
Font family:    "Noto Serif JP", serif
Color:          #1A1A1A
Placeholder:    #6B6B6B
Focus outline:  2px solid #1A1A1A
Label:          font-weight: Bold, font-size: 14px, text-transform: uppercase, letter-spacing: 0.1em
```

### Navigation
```
Height:         auto（新聞のマストヘッドはフレキシブル）
Background:     #FBF7F0
Border-bottom:  3px double #1A1A1A（二重線 — 新聞のヘッダー罫線）
Logo:           新聞のマストヘッド風。大きなセリフ体のテキストロゴ
               font-size: 48px / font-weight: 700 / letter-spacing: 0.12em
Link spacing:   28px
Link color:     #1A1A1A
Link hover:     #8B0000
Active link:    #8B0000, border-bottom: 2px solid #8B0000
Sections bar:   ナビ下にカテゴリーバー。背景: #F0EBE1, border: 1px solid #1A1A1A
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    60px（モバイルは 20px）
Section spacing:  48px（紙面は比較的詰めたレイアウト）
Grid columns:     12
Gutter:           24px
```

**マルチカラムレイアウト**
```
- デスクトップ: 2〜3カラムレイアウトが基本
- メイン記事: 2カラム（8:4 または 6:6 のグリッド比率）
- 記事一覧: 3カラム（4:4:4）
- CSS column-count も活用可: column-count: 2, column-gap: 32px, column-rule: 1px solid #1A1A1A
- モバイル: シングルカラムにフォールバック
```

**ラインセパレータ**
```
- セクション区切り: border-top: 1px solid #1A1A1A
- 重要な区切り: border-top: 3px double #1A1A1A（二重線）
- カラム間: column-rule: 1px solid #1A1A1A
- 最も重要な区切り（一面トップ下）: border-top: 6px solid #1A1A1A
```

---

## Do's and Don'ts

### Do
- セリフ体を一貫して使い、新聞の格式を保つ
- 記事の先頭にドロップキャップ（大きな先頭文字）を配置する
- カラム間に縦のラインセパレータ（column-rule）を入れる
- 見出しの下に1pxのルール線を引いて階層を明確にする
- 画像にはalt属性とキャプション（イタリック+小さめサイズ）を必ず付ける

### Don't
- 角丸を使わない。新聞デザインはすべてシャープな直角
- ドロップシャドウを使わない。新聞はフラットな紙面
- カラフルな色を多用しない。基本はモノクロ + アクセントの赤のみ
- アニメーションや派手なトランジションを使わない
- フォントをサンセリフに変更しない（UIの極小テキスト以外）

---

*Design: 38-newspaper — Newspaper Editorial UI*
