# DESIGN.md — 36: グラデーションメッシュ

> Apple最新OS風の複雑なグラデーション背景を使った、没入感のあるビジュアルデザイン。  
> メッシュグラデーション（複数色の滑らかなブレンド）とグロー効果で幻想的な空間を演出。

---

## Project Overview

- **Project Name**: Gradient Mesh UI
- **Vibe**: "宇宙的で没入感のあるビジュアル。AppleのvisionOS/macOS風の美しいメッシュグラデーションが背景を彩る"
- **Target User**: クリエイター、デザイナー、先端テクノロジーに関心の高いユーザー

---

## Color Palette & Roles

```
Primary:      #7C3AED   （メインCTA・リンク・ブランドカラー。バイオレット）
Secondary:    #A855F7   （サブアクション・ホバー状態。ライトパープル）
Background:   #0F0F23   （ページ背景。深いダークネイビー）
Surface:      #1E1B4B   （カード・セクション背景。インディゴブラック）
Text:         #F8FAFC   （本文テキスト。ほぼ白）
Text-muted:   #94A3B8   （補足テキスト・キャプション。スレートグレー）
Accent:       #EC4899   （強調・バッジ・グロー効果。ホットピンク）
Border:       rgba(255,255,255,0.1) （区切り線・枠線。半透明ホワイト）
```

**メッシュグラデーション用の追加カラー**
```
Mesh-1:       #7C3AED   （バイオレット）
Mesh-2:       #EC4899   （ピンク）
Mesh-3:       #3B82F6   （ブルー）
Mesh-4:       #06B6D4   （シアン）
```

**コントラスト比の必須要件**
- Body text（#F8FAFC on #0F0F23）: 約16.5:1 ✓（WCAG AAA）
- Text-muted（#94A3B8 on #0F0F23）: 約7.2:1 ✓（WCAG AA）
- Primary on Background（#7C3AED on #0F0F23）: 約4.8:1 ✓（WCAG AA Large）

---

## Typography Rules

```
Font:          "Inter", sans-serif
Font-en:       "Inter", sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、40px — グロー効果あり（text-shadow: 0 0 40px rgba(124,58,237,0.5)）
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**特殊ルール**
- 見出しにはオプションでグロー効果（text-shadow）を適用可
- 数字・英字にはtabular-numsを使用
- font-smoothing: antialiased を必ず指定（ダーク背景でのテキスト品質向上）

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        14px 28px
Min width:      140px
Font weight:    SemiBold（600）
Font size:      15px

Primary button:
  background: linear-gradient(135deg, #7C3AED, #EC4899)
  color: #FFFFFF
  box-shadow: 0 0 20px rgba(124,58,237,0.4)
  hover: box-shadow: 0 0 30px rgba(124,58,237,0.6)

Secondary button:
  background: rgba(255,255,255,0.05)
  backdrop-filter: blur(12px)
  border: 1px solid rgba(255,255,255,0.15)
  color: #F8FAFC
  hover: background: rgba(255,255,255,0.1)

Ghost button:
  background: transparent
  border: none
  color: #A855F7
  hover: color: #C084FC
```

### Card
```
Border radius:  16px
Padding:        28px
Border:         1px solid rgba(255,255,255,0.1)
Background:     rgba(30,27,75,0.6)
Backdrop-filter: blur(20px)
Shadow:         0 8px 32px rgba(0,0,0,0.3)
Hover shadow:   0 8px 32px rgba(124,58,237,0.15)
```

### Input / Form
```
Border radius:  10px
Border:         1px solid rgba(255,255,255,0.15)
Background:     rgba(255,255,255,0.05)
Padding:        12px 16px
Font size:      16px
Color:          #F8FAFC
Placeholder:    #94A3B8
Focus outline:  2px solid #7C3AED
Focus glow:     0 0 12px rgba(124,58,237,0.3)
```

### Navigation
```
Height:         72px
Background:     rgba(15,15,35,0.8)
Backdrop-filter: blur(20px)
Border-bottom:  1px solid rgba(255,255,255,0.06)
Logo width:     120px
Link spacing:   36px
Link color:     #94A3B8
Link hover:     #F8FAFC
Active link:    #7C3AED with glow
```

---

## Layout Principles

```
Max width:        1280px
Outer padding:    80px（モバイルは 24px）
Section spacing:  120px（ゆとりある大胆な余白）
Grid columns:     12
Gutter:           32px
```

**メッシュグラデーション背景の配置**
```
- ページ全体の背景に position: fixed で mesh gradient を配置
- CSS: background-image に複数の radial-gradient を重ねる
  例: radial-gradient(ellipse at 20% 50%, rgba(124,58,237,0.3), transparent 50%),
      radial-gradient(ellipse at 80% 20%, rgba(236,72,153,0.2), transparent 50%),
      radial-gradient(ellipse at 60% 80%, rgba(59,130,246,0.2), transparent 50%)
- アニメーション: 位置を緩やかに変化させる（20-30秒周期）
```

---

## Do's and Don'ts

### Do
- メッシュグラデーションは背景のみに使い、コンテンツの可読性を優先する
- カード・モーダルには必ず `backdrop-filter: blur()` を適用してグラスモーフィズムにする
- ボタンやインタラクティブ要素にはグロー効果（box-shadow）を使って目立たせる
- 画像にはalt属性を必ず付ける
- ダーク背景では `-webkit-font-smoothing: antialiased` を必ず指定

### Don't
- メッシュグラデーションの色を4色以上同時に使わない（ノイジーになる）
- テキストの上に直接強いグラデーションを置かない（可読性が下がる）
- グロー効果を全要素に適用しない（重要な要素のみ）
- `backdrop-filter` のblur値を40px以上にしない（パフォーマンス低下）
- フォントを Inter 以外に変更しない

---

*Design: 36-gradient-mesh — Gradient Mesh UI*
