# DESIGN.md — ドット・ポルカ柄風

> レトロポップなドットパターンで遊び心を表現するデザインシステム。  
> 丸みのあるシェイプとポップな配色で、楽しくフレンドリーな印象を与える。

---

## Project Overview

- **Project Name**: ドット・ポルカ柄風デザイン
- **Vibe**: "レトロポップな遊び心。ドット柄と丸いフォルムで、楽しさと親しみやすさを伝える"
- **Target User**: 若年層向けのライフスタイルブランド、カジュアルなECサイトの利用者

---

## Color Palette & Roles

```
Primary:      #FF6B6B   （メインCTA・リンク・ブランドカラー。コーラルレッド）
Secondary:    #FFE66D   （サブアクション・タグ。レモンイエロー）
Background:   #FFFCF9   （ページ背景。ほぼ白のウォームトーン）
Surface:      #FFF0EB   （カード・セクション背景。淡いピーチ）
Text:         #2D3436   （本文テキスト。チャコール）
Text-muted:   #636E72   （補足テキスト・キャプション）
Accent:       #4ECDC4   （強調・バッジ。ミントグリーン）
Border:       #FFE0D6   （区切り線・枠線。淡いピーチボーダー）
```

**コントラスト比の必須要件**
- Body text（#2D3436 on #FFFCF9）: 約 13.8:1（WCAG AAA適合）
- Text-muted（#636E72 on #FFFCF9）: 約 5.5:1（WCAG AA適合）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "DM Sans", sans-serif
Font-ja:       "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: Medium（500）、22px
  H4: Medium（500）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**スタイルノート**
- DM Sans の丸みのある字形がポルカドットの雰囲気に合う
- 見出しには太めのウェイトを使い、ポップ感を出す
- 日本語テキストには Noto Sans JP を使用

---

## Component Stylings

### Button
```
Border radius:  50px（完全カプセル型。丸い印象を徹底）
Padding:        14px 32px
Min width:      130px
Font weight:    Bold（700）
Font size:      16px

Primary button:
  background: #FF6B6B
  color: #FFFFFF
  border: none
  box-shadow: 0 4px 12px rgba(255,107,107,0.3)
  hover → background: #FF5252, transform: translateY(-2px)
  active → transform: translateY(0)
  transition: all 0.2s ease

Secondary button:
  background: #FFFFFF
  border: 2px solid #FF6B6B
  color: #FF6B6B
  hover → background: #FFF0EB

Accent button:
  background: #4ECDC4
  color: #FFFFFF
  border: none
  box-shadow: 0 4px 12px rgba(78,205,196,0.3)
  hover → background: #45B7AA
```

### Card
```
Border radius:  20px（大きめの丸角でポップに）
Padding:        24px
Border:         2px solid #FFE0D6
Background:     #FFFFFF
Shadow:         0 4px 16px rgba(255,107,107,0.08)

ホバー時:
  transform: translateY(-4px)
  shadow: 0 8px 24px rgba(255,107,107,0.15)
  transition: all 0.3s ease
```

### Input / Form
```
Border radius:  50px（ボタンと同じカプセル型）
Border:         2px solid #FFE0D6
Padding:        12px 20px
Font size:      16px
Background:     #FFFFFF
Focus:
  border-color: #FF6B6B
  box-shadow: 0 0 0 4px rgba(255,107,107,0.15)
  outline: none
Placeholder:    color #636E72
```

### Navigation
```
Height:         68px
Background:     #FFFFFF
Border-bottom:  2px solid #FFE0D6
Logo width:     120px
Link spacing:   32px
Link style:     color: #2D3436, font-weight: 500
Hover:          color: #FF6B6B
Active:         color: #FF6B6B, font-weight: 700
                position relative + ::after で丸ドットインジケーター
                （width: 6px, height: 6px, border-radius: 50%, background: #FF6B6B）
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    72px（モバイルは 20px）
Section spacing:  96px
Grid columns:     12
Gutter:           32px

ドットパターン背景の実装:
  background-image: radial-gradient(circle, #FFE0D6 1.5px, transparent 1.5px);
  background-size: 24px 24px;
  ※ セクション背景やヒーローエリアに薄く適用
  ※ opacity: 0.5〜0.7 で控えめにする

SVGドットパターン例:
  <pattern id="dots" x="0" y="0" width="24" height="24" patternUnits="userSpaceOnUse">
    <circle cx="12" cy="12" r="2" fill="#FFE0D6" />
  </pattern>

特記事項:
- 丸みのあるシェイプを一貫して使用する
- イラストやアイコンも丸角・丸フォルムに統一
- ドットパターンは背景装飾として使い、テキストの可読性を妨げない
```

---

## Do's and Don'ts

### Do
- border-radius: 50px のカプセル型をボタン・入力欄に一貫して使う
- ドットパターンを背景装飾に活用する（radial-gradient または SVG）
- ポップなカラーリング（コーラル + ミント + レモン）を組み合わせて使う
- ホバー時に軽い浮き上がりアニメーション（translateY）を加える
- DM Sans / Noto Sans JP の2書体のみ使用する

### Don't
- 角張ったシェイプ（border-radius: 0）を使わない
- ダークな配色やモノトーンに寄せない
- ドットパターンをテキスト領域の直下に配置しない（可読性低下）
- ボタンやカードの影を真っ黒にしない（カラーシャドウを使う）
- 3色以上のアクセントカラーを同時に表示しない
- コントラスト比 4.5:1 を下回るテキストを置かない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
