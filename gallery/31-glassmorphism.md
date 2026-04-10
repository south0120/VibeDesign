# DESIGN.md — グラスモーフィズム

---

## Project Overview

- **Project Name**: グラスモーフィズム — すりガラスの透明レイヤー
- **Vibe**: "すりガラス風の半透明カード。奥行きとレイヤーが生む美しい階層構造"
- **Target User**: モダンなSaaS、ダッシュボード、ポートフォリオ

---

## Color Palette & Roles

```
Primary:      #667EEA   （メインCTA・グラデーション起点）
Secondary:    #764BA2   （グラデーション終点）
Background:   #667EEA   （グラデーション背景: linear-gradient(135deg, #667EEA, #764BA2)）
Surface:      rgba(255,255,255,0.25)（すりガラスカード）
Text:         #FFFFFF   （本文テキスト）
Text-muted:   rgba(255,255,255,0.6)（補足テキスト）
Accent:       #F093FB   （ハイライト・バッジ）
Border:       rgba(255,255,255,0.18)（ガラスボーダー）
```

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: 0em

Heading weights:
  H1: Bold（700）、48px
  H2: SemiBold（600）、32px
  H3: SemiBold（600）、22px
  H4: Medium（500）、18px
Body: Regular（400）、16px
```

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        14px 28px
Font weight:    SemiBold（600）
background:     rgba(255,255,255,0.2)
backdrop-filter: blur(10px)
border:         1px solid rgba(255,255,255,0.3)
color:          #FFFFFF
Hover:          background rgba(255,255,255,0.35)
```

### Card
```
Border radius:  16px
Padding:        32px
Background:     rgba(255,255,255,0.25)
backdrop-filter: blur(16px) saturate(180%)
Border:         1px solid rgba(255,255,255,0.18)
Shadow:         0 8px 32px rgba(0,0,0,0.1)
```

### Navigation
```
Height:         64px
Background:     rgba(255,255,255,0.15)
backdrop-filter: blur(20px)
Border bottom:  1px solid rgba(255,255,255,0.1)
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    48px（モバイル 20px）
Section spacing:  96px
Grid columns:     12
Gutter:           24px
```

---

## Do's and Don'ts

### Do
- backdrop-filter: blur() を活用する
- 背景にグラデーションやイメージを置いてガラス効果を活かす
- ボーダーは半透明白（rgba）で統一する

### Don't
- 不透明な背景色をカードに使わない
- blur値を小さくしすぎない（16px以上推奨）
- テキストの可読性を犠牲にしない

---

*Design Style: Glassmorphism — 2026-04-10*

---

## CSS / Component Examples

```css
/* グラスモーフィズム カード */
.glass-card {
  background: rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(16px) saturate(180%);
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.18);
  box-shadow: 0 8px 32px rgba(31, 38, 135, 0.15);
}

/* グラデーション背景 */
.glass-bg {
  background: linear-gradient(135deg, #667EEA 0%, #764BA2 100%);
  min-height: 100vh;
}

/* グラスボタン */
.glass-btn {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
  border-radius: 12px;
  padding: 12px 24px;
  color: #fff;
  transition: background 0.3s;
}
.glass-btn:hover { background: rgba(255, 255, 255, 0.35); }
```
