# DESIGN.md — レトロ・ヴィンテージ風

> 70年代のアナログ感とセピア調の暖かみを持つデザインシステム。  
> Letterpress風テクスチャと落ち着いたトーンで、懐かしさと信頼感を演出する。

---

## Project Overview

- **Project Name**: レトロ・ヴィンテージ風デザイン
- **Vibe**: "70年代のレコードジャケットを思わせるアナログな温もり。セピア調の暖かみで懐かしさと信頼を伝える"
- **Target User**: レトロカルチャーを愛好するクリエイター、ヴィンテージショップ運営者

---

## Color Palette & Roles

```
Primary:      #D4A574   （メインCTA・リンク・ブランドカラー。暖かみのあるキャメル）
Secondary:    #A67C52   （サブアクション・タグ。少し深いブラウン）
Background:   #FFF8F0   （ページ背景。クリーム色で紙のような質感）
Surface:      #F5E6D3   （カード・セクション背景。薄いベージュ）
Text:         #3D2B1F   （本文テキスト。ダークブラウン）
Text-muted:   #8B7355   （補足テキスト・キャプション。ミディアムブラウン）
Accent:       #C75C2A   （強調・警告・バッジ。テラコッタオレンジ）
Border:       #D4C4B0   （区切り線・枠線。暖かみのあるベージュ）
```

**コントラスト比の必須要件**
- Body text（#3D2B1F on #FFF8F0）: 約 12.5:1（WCAG AAA適合）
- Text-muted（#8B7355 on #FFF8F0）: 約 4.6:1（WCAG AA適合）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Playfair Display", serif
Font-ja:       "Noto Serif JP", serif
Base size:     16px
Line height:   1.8
Letter spacing: 0.03em（日本語テキスト用。英語は 0.01em）

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**スタイルノート**
- 見出しには Playfair Display を使い、クラシカルなセリフ感を強調する
- 本文は Noto Serif JP で和文の可読性を確保する
- text-transform: uppercase は英語見出しに適宜使用する

---

## Component Stylings

### Button
```
Border radius:  0px（角丸なし。シャープでクラシカルな印象）
Padding:        14px 28px
Min width:      140px
Font weight:    Bold（700）
Font size:      15px
Text transform: uppercase
Letter spacing: 0.08em

Primary button:
  background: transparent
  border: 2px solid #D4A574
  color: #3D2B1F
  hover → background: #D4A574, color: #FFF8F0

Secondary button:
  background: transparent
  border: 2px solid #D4C4B0
  color: #8B7355
  hover → background: #F5E6D3, color: #3D2B1F

Accent button:
  background: transparent
  border: 2px solid #C75C2A
  color: #C75C2A
  hover → background: #C75C2A, color: #FFF8F0
```

### Card
```
Border radius:  0px（角丸なし）
Padding:        28px
Border:         2px solid #D4C4B0
Shadow:         none（影ではなくボーダーで区切る）
Background:     #FFF8F0

ホバー時:
  border-color: #D4A574
  transition: border-color 0.3s ease
```

### Input / Form
```
Border radius:  0px
Border:         2px solid #D4C4B0
Padding:        12px 16px
Font size:      16px
Font family:    "Playfair Display", serif
Background:     #FFF8F0
Focus outline:  2px solid #D4A574
Placeholder:    color #8B7355, font-style italic
```

### Navigation
```
Height:         72px
Background:     #FFF8F0
Border-bottom:  2px solid #D4C4B0
Logo width:     140px
Link spacing:   36px
Link style:     text-transform: uppercase, letter-spacing: 0.06em, color: #3D2B1F
Hover:          color: #C75C2A, text-decoration: underline
Active:         border-bottom: 2px solid #D4A574
```

---

## Layout Principles

```
Max width:        1080px（少し狭めで雑誌的なレイアウト）
Outer padding:    80px（モバイルは 24px）
Section spacing:  80px
Grid columns:     12
Gutter:           28px

特記事項:
- コンテンツは中央寄せ
- 写真にはセピアフィルター（filter: sepia(20%) contrast(1.05)）を適用
- 背景テクスチャとして紙のノイズパターンを薄く重ねる
  （background-image で noise.png を opacity 0.03 程度）
- 区切り線にはダブルボーダー（border-style: double）も活用
```

---

## Do's and Don'ts

### Do
- ボーダーを主体としたデザインを徹底する（角丸は使わない）
- text-transform: uppercase と letter-spacing でクラシカルな雰囲気を出す
- セリフ体（Playfair Display / Noto Serif JP）のみ使用する
- 写真にはセピア系フィルターを統一して適用する
- 余白を広めに取り、雑誌のような余裕のあるレイアウトにする

### Don't
- 角丸（border-radius）を使わない
- グラデーション背景を使わない
- ネオン色や彩度の高い色を使わない
- ゴシック体・サンセリフフォントを混ぜない
- ボックスシャドウに頼らない（ボーダーで表現する）
- 過度なアニメーションを使わない（トランジションは控えめに 0.3s 以内）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
