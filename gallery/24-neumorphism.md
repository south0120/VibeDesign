# DESIGN.md — ニューモーフィズム

> ソフトな押し出しと凹みで触覚的なUI体験を実現するデザインシステム。  
> ボーダーを使わず、光と影のみでインターフェースの奥行きを表現する。

---

## Project Overview

- **Project Name**: ニューモーフィズムデザイン
- **Vibe**: "やわらかく触れたくなるUI。光と影だけで形作られた、触覚的でミニマルな世界観"
- **Target User**: プレミアム感を求めるダッシュボード利用者、ウェルネス・瞑想系アプリのユーザー

---

## Color Palette & Roles

```
Primary:      #6C63FF   （メインCTA・リンク・ブランドカラー。パープル）
Secondary:    #A29BFE   （サブアクション・タグ。ライトパープル）
Background:   #E0E5EC   （ページ背景。ニューモーフィズムの基盤色）
Surface:      #E0E5EC   （カード・セクション背景。背景と同色）
Text:         #2D3748   （本文テキスト。ダークネイビー）
Text-muted:   #718096   （補足テキスト・キャプション）
Accent:       #FF6584   （強調・警告・バッジ。コーラルピンク）
Border:       none       （ボーダーは使用しない。影のみで表現）
```

**コントラスト比の必須要件**
- Body text（#2D3748 on #E0E5EC）: 約 7.1:1（WCAG AAA適合）
- Text-muted（#718096 on #E0E5EC）: 約 3.6:1（Large textのみWCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Inter", sans-serif
Font-ja:       "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0em

Heading weights:
  H1: Bold（700）、32px
  H2: Bold（700）、24px
  H3: SemiBold（600）、20px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**スタイルノート**
- Inter のニュートラルな字形がニューモーフィズムの控えめな世界観に合う
- フォントウェイトは控えめに使い、影の表現を主役にする
- テキストカラーは背景色とのコントラストを必ず確保する

---

## Component Stylings

### Button
```
Border radius:  16px
Padding:        14px 28px
Min width:      130px
Font weight:    SemiBold（600）
Font size:      16px

共通シャドウ（凸状態 / デフォルト）:
  box-shadow: 8px 8px 16px #b8bec7, -8px -8px 16px #ffffff

Primary button:
  background: #E0E5EC
  color: #6C63FF
  border: none
  box-shadow: 8px 8px 16px #b8bec7, -8px -8px 16px #ffffff
  hover → box-shadow: 6px 6px 12px #b8bec7, -6px -6px 12px #ffffff
  active（押下状態）→ box-shadow: inset 8px 8px 16px #b8bec7, inset -8px -8px 16px #ffffff
  transition: box-shadow 0.2s ease

Accent button:
  background: #6C63FF
  color: #FFFFFF
  border: none
  box-shadow: 8px 8px 16px #b8bec7, -8px -8px 16px #ffffff
  hover → box-shadow: 6px 6px 12px #b8bec7, -6px -6px 12px #ffffff
  active → box-shadow: inset 4px 4px 8px rgba(0,0,0,0.15)
```

### Card
```
Border radius:  20px
Padding:        28px
Border:         none（ボーダーなし）
Background:     #E0E5EC
Shadow（凸）:   8px 8px 16px #b8bec7, -8px -8px 16px #ffffff

凹バリエーション（インセット）:
  box-shadow: inset 8px 8px 16px #b8bec7, inset -8px -8px 16px #ffffff

ホバー時:
  box-shadow: 10px 10px 20px #b8bec7, -10px -10px 20px #ffffff
  transition: box-shadow 0.3s ease
```

### Input / Form
```
Border radius:  12px
Border:         none
Padding:        14px 18px
Font size:      16px
Background:     #E0E5EC
Box-shadow（凹）: inset 4px 4px 8px #b8bec7, inset -4px -4px 8px #ffffff
Focus:
  box-shadow: inset 6px 6px 12px #b8bec7, inset -6px -6px 12px #ffffff,
              0 0 0 3px rgba(108,99,255,0.3)
  outline: none
Placeholder:    color #718096
```

### Navigation
```
Height:         68px
Background:     #E0E5EC
Border-bottom:  none（影で区切る）
Box-shadow:     0 4px 8px #b8bec7
Logo width:     120px
Link spacing:   32px
Link style:     color: #2D3748, font-weight: 500
Hover:          color: #6C63FF
Active:
  background: #E0E5EC でピル型（border-radius: 10px, padding: 6px 16px）
  box-shadow: inset 3px 3px 6px #b8bec7, inset -3px -3px 6px #ffffff
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    80px（モバイルは 24px）
Section spacing:  96px
Grid columns:     12
Gutter:           32px

特記事項:
- 背景色とSurface色は同一（#E0E5EC）。影だけで要素を浮き立たせる
- 凸（浮き出し）と凹（くぼみ）を明確に使い分ける
  - 凸: カード、ボタン（デフォルト）、アイコン
  - 凹: 入力欄、プログレスバーのトラック、アクティブ状態
- 影の色は背景色から計算する
  - 暗い影: 背景色を 15-20% 暗くした色
  - 明るい影: #FFFFFF
- 要素間の余白を広く取り、影が潰れないようにする（最低 24px）
```

---

## Do's and Don'ts

### Do
- すべての要素を box-shadow のみで表現する（border は使わない）
- 背景色とSurface色を揃え、同一平面上に見せる
- 凸と凹の使い分けでインタラクション状態を示す
- 影の blur 値は要素サイズに比例させる（小要素: 8px、大要素: 16-20px）
- Inter / Noto Sans JP の2書体のみ使用する

### Don't
- border を使わない（影のみで区切る）
- 背景色と異なる色のカードを作らない（ニューモーフィズムが崩れる）
- 影の色をハードコードせず、背景色との相対値で設定する
- 要素を密に配置しない（影が重なって汚くなる）
- 濃い背景色や暗い色を使わない（影のコントラストが出にくくなる）
- コントラスト比 4.5:1 を下回るテキストを置かない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*

---

## CSS / Component Examples

```css
/* ニューモーフィズム 凸ボタン */
.neu-btn {
  background: #E0E5EC;
  border: none;
  border-radius: 12px;
  padding: 16px 32px;
  box-shadow: 8px 8px 16px #b8bec7, -8px -8px 16px #ffffff;
  transition: all 0.2s;
}
.neu-btn:active {
  box-shadow: inset 4px 4px 8px #b8bec7, inset -4px -4px 8px #ffffff;
}

/* ニューモーフィズム 凹インプット */
.neu-input {
  background: #E0E5EC;
  border: none;
  border-radius: 10px;
  padding: 14px 18px;
  box-shadow: inset 4px 4px 8px #b8bec7, inset -4px -4px 8px #ffffff;
}

/* ニューモーフィズム カード */
.neu-card {
  background: #E0E5EC;
  border-radius: 20px;
  padding: 32px;
  box-shadow: 12px 12px 24px #b8bec7, -12px -12px 24px #ffffff;
}
```
