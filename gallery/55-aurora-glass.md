# DESIGN.md — オーロラグラス

---

## Project Overview

- **Project Name**: オーロラグラス — iOS meets 北欧オーロラ
- **Vibe**: "リキッドグラスとオーロラグラデーションの融合。透明感と幻想的な光のレイヤー"
- **Target User**: AI・テクノロジープロダクト、プレミアムSaaS

---

## Color Palette & Roles

```
Primary:      #818CF8   （メインCTA・インディゴ）
Secondary:    #6EE7B7   （サブ・オーロラグリーン）
Background:   #0F172A   （ページ背景・ディープネイビー）
Surface:      rgba(30, 41, 59, 0.7)（すりガラスカード）
Text:         #E2E8F0   （本文テキスト）
Text-muted:   #64748B   （補足テキスト）
Accent:       #F0ABFC   （ピンクグロー）
Border:       rgba(129, 140, 248, 0.2)（インディゴグロー）
```

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.6
H1: Bold 52px / H2: SemiBold 36px / H3: SemiBold 22px
```

---

## Component Stylings

### Button
```
Border radius:  14px
Padding:        14px 28px
Primary: background #818CF8, color #FFFFFF, box-shadow 0 0 24px rgba(129,140,248,0.4)
Secondary: transparent, border 1px solid rgba(129,140,248,0.4), color #818CF8
```

### Card
```
Border radius:  20px
Padding:        32px
Background:     rgba(30, 41, 59, 0.7)
backdrop-filter: blur(24px) saturate(180%)
Border:         1px solid rgba(129, 140, 248, 0.15)
```

### Navigation
```
Height:         60px
Background:     rgba(15, 23, 42, 0.8)
backdrop-filter: blur(24px)
```

---

## Layout Principles

```
Max width:        1100px
Section spacing:  100px
```

---

## CSS / Component Examples

```css
/* オーロラグラデーション背景 */
.aurora-bg {
  background: #0F172A;
  position: relative;
  overflow: hidden;
}
.aurora-bg::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: conic-gradient(
    from 0deg at 50% 50%,
    #818CF8 0deg,
    #6EE7B7 90deg,
    #F0ABFC 180deg,
    #818CF8 270deg,
    #6EE7B7 360deg
  );
  opacity: 0.15;
  filter: blur(100px);
  animation: aurora-rotate 20s linear infinite;
}
@keyframes aurora-rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* オーロラグラスカード */
.aurora-card {
  background: rgba(30, 41, 59, 0.6);
  backdrop-filter: blur(24px) saturate(180%);
  border: 1px solid rgba(129, 140, 248, 0.15);
  border-radius: 20px;
  padding: 32px;
  box-shadow: 0 0 40px rgba(129, 140, 248, 0.08);
}

/* グローボタン */
.aurora-btn {
  background: #818CF8;
  color: #fff;
  border: none;
  border-radius: 14px;
  padding: 14px 28px;
  box-shadow: 0 0 24px rgba(129, 140, 248, 0.4);
  transition: box-shadow 0.3s;
}
.aurora-btn:hover {
  box-shadow: 0 0 40px rgba(129, 140, 248, 0.6);
}
```

---

## Do's and Don'ts

### Do
- 背景にconic-gradientのオーロラアニメーション
- カードにbackdrop-filter + グローボーダー
- ボタンにbox-shadowグロー

### Don't
- 明るい背景にしない
- グローを全要素につけすぎない
- オーロラの色を4色以上使わない

---

*Design Style: Aurora Glass — 2026-04-10*
