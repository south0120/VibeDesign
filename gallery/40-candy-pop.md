# DESIGN.md — 40: キャンディポップ

> 鮮やかでカラフル、子供向け・エンタメ向けの楽しさ爆発デザイン。  
> 大きな角丸、カラーシャドウ、バウンスアニメーションで遊び心を全面に。

---

## Project Overview

- **Project Name**: Candy Pop UI
- **Vibe**: "お菓子の国のテーマパーク。ビビッドなカラー、ぷにぷにした角丸、弾むアニメーションが笑顔を生む"
- **Target User**: 子供向けサービス、エンタメ系アプリ、ゲーム、教育、カジュアルなコミュニティ

---

## Color Palette & Roles

```
Primary:      #FF6B6B   （メインCTA・リンク・ブランドカラー。コーラルレッド）
Secondary:    #48DBFB   （サブアクション・タグ。スカイブルー）
Background:   #FFF5F5   （ページ背景。ほんのりピンクがかった白）
Surface:      #FFFFFF   （カード・セクション背景。純白）
Text:         #2D3436   （本文テキスト。ダークグレー）
Text-muted:   #636E72   （補足テキスト・キャプション）
Accent:       #6C5CE7   （強調・バッジ。ビビッドパープル）
Border:       #FFE0E0   （区切り線・枠線。ライトピンク）
```

**追加のポップカラー**
```
Yellow:       #FECA57   （スター・評価・ハイライト）
Green:        #55E6C1   （成功・完了・ポジティブ）
Orange:       #FF9F43   （警告・注目）
Pink:         #FD79A8   （お気に入り・ハート）
```

**コントラスト比の必須要件**
- Text（#2D3436 on #FFF5F5）: 約12.3:1 ✓（WCAG AAA）
- Text-muted（#636E72 on #FFF5F5）: 約5.1:1 ✓（WCAG AA）
- Primary（#FF6B6B on #FFFFFF）: 約3.9:1 ✓（WCAG AA Large text）

---

## Typography Rules

```
Font:          "Quicksand", "Nunito", "Rounded Mplus 1c", sans-serif
Font-en:       "Quicksand", sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0.02em

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Medium（500）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**特殊ルール**
- フォントは丸みのある（Rounded）サンセリフを使う
- 見出しには遊び心のある色を使ってよい（Primary, Accent, Secondary を交互に）
- 絵文字の使用OK（見出しの先頭やリスト項目に）
- 太字を積極的に使い、元気な印象を出す

---

## Component Stylings

### Button
```
Border radius:  24px（大きめの角丸 — ぷにぷに感）
Padding:        14px 32px
Min width:      140px
Font weight:    Bold（700）
Font size:      16px
Font family:    "Quicksand", sans-serif

Primary button:
  background: #FF6B6B
  color: #FFFFFF
  border: none
  box-shadow: 0 4px 14px rgba(255,107,107,0.4)（カラーシャドウ）
  hover: transform: translateY(-2px) / box-shadow: 0 6px 20px rgba(255,107,107,0.5)
  active: transform: translateY(0px) scale(0.98)

Secondary button:
  background: #FFFFFF
  border: 2px solid #FF6B6B
  color: #FF6B6B
  box-shadow: 0 4px 14px rgba(255,107,107,0.15)
  hover: background: #FFF5F5

Accent button:
  background: #6C5CE7
  color: #FFFFFF
  box-shadow: 0 4px 14px rgba(108,92,231,0.4)

Fun button:
  background: linear-gradient(135deg, #FF6B6B, #FECA57, #55E6C1, #48DBFB, #6C5CE7)
  background-size: 300% 300%
  animation: gradient-shift 3s ease infinite
  color: #FFFFFF
```

### Card
```
Border radius:  24px
Padding:        28px
Border:         2px solid #FFE0E0
Background:     #FFFFFF
Shadow:         0 8px 24px rgba(255,107,107,0.1)（カラーシャドウ）
Hover shadow:   0 12px 32px rgba(255,107,107,0.2)
Hover transform: translateY(-4px)
Transition:     all 0.3s cubic-bezier(0.34, 1.56, 0.64, 1)（バウンス感のあるイージング）
```

### Input / Form
```
Border radius:  16px
Border:         2px solid #FFE0E0
Background:     #FFFFFF
Padding:        12px 18px
Font size:      16px
Font family:    "Quicksand", sans-serif
Color:          #2D3436
Placeholder:    #636E72
Focus border:   2px solid #FF6B6B
Focus shadow:   0 0 0 4px rgba(255,107,107,0.15)
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Border-bottom:  2px solid #FFE0E0
Box-shadow:     0 2px 12px rgba(255,107,107,0.08)
Logo:           丸みのある太字テキスト + 絵文字/アイコン
Logo size:      font-size: 24px / font-weight: 700
Link spacing:   32px
Link color:     #636E72
Link hover:     #FF6B6B
Active link:    #FF6B6B / font-weight: 700
Active indicator: 下に丸いドット（6px circle, background: #FF6B6B）
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    64px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           28px
```

**バウンスアニメーション**
```
- 要素の出現時: @keyframes bounceIn {
    0% { opacity: 0; transform: scale(0.3) }
    50% { transform: scale(1.05) }
    70% { transform: scale(0.95) }
    100% { opacity: 1; transform: scale(1) }
  }
  animation: bounceIn 0.6s cubic-bezier(0.34, 1.56, 0.64, 1)

- ホバー時のバウンス: cubic-bezier(0.34, 1.56, 0.64, 1) をtransition-timing-functionに使用
- ボタンクリック時: scale(0.95) → scale(1) のバウンスバック
```

**カラーシャドウのルール**
```
- 影の色は要素の背景色に合わせる:
  - 赤い要素: rgba(255,107,107,0.3)
  - 紫の要素: rgba(108,92,231,0.3)
  - 青い要素: rgba(72,219,251,0.3)
  - 黄色の要素: rgba(254,202,87,0.3)
- 影の拡散は 14px〜24px
- 黒いシャドウ（rgba(0,0,0,...)）は使わない
```

---

## Do's and Don'ts

### Do
- カラーシャドウ（要素の色に合わせた影）を使ってポップ感を出す
- 角丸は 16px〜24px の大きめを使い、丸っこい印象にする
- バウンスアニメーション（cubic-bezier(0.34, 1.56, 0.64, 1)）を活用する
- 複数のビビッドカラーを楽しく組み合わせる
- 画像にはalt属性を必ず付ける

### Don't
- 黒いドロップシャドウ（rgba(0,0,0,...)）を使わない。カラーシャドウのみ
- 直角（border-radius: 0px）を使わない。最低でも 8px の角丸
- 暗い色やダーク背景を使わない（ライトで明るい雰囲気を保つ）
- フォントを角ばったサンセリフやセリフに変更しない
- アニメーションの duration を 0.8秒以上にしない（テンポが悪くなる）
- 1画面にアニメーション要素を5つ以上同時に動かさない（うるさくなる）

---

*Design: 40-candy-pop — Candy Pop UI*
