# DESIGN.md — レトロターミナル（琥珀）

---

## Project Overview

- **Project Name**: レトロターミナル（琥珀） — CRTの温もり
- **Vibe**: "琥珀色のCRT画面。フリッカーカーソルとスキャンラインが醸す、レトロコンピューティングの世界"
- **Target User**: 開発者ブログ、ハッカーツール、レトロゲーム

---

## Color Palette & Roles

```
Primary:      #FFB000   （メインCTA・アンバー）
Secondary:    #FF6600   （サブ・オレンジ）
Background:   #1A0F00   （ページ背景・ダークブラウン）
Surface:      #261800   （カード背景）
Text:         #FFB000   （本文テキスト・アンバー）
Text-muted:   #8B6914   （補足テキスト・暗いアンバー）
Accent:       #FF6600   （警告・エラー）
Border:       #3D2800   （ボーダー）
```

---

## Typography Rules

```
Font:          "VT323", "Courier New", monospace
Base size:     18px
Line height:   1.6
全テキスト monospace。ウェイトは Regular のみ。
H1: 36px / H2: 28px / H3: 22px
```

---

## Component Stylings

### Button
```
Border radius:  0px
Padding:        10px 24px
Border:         2px solid #FFB000
Background:     transparent
Color:          #FFB000
text-shadow:    0 0 8px rgba(255, 176, 0, 0.5)
```

### Card
```
Border radius:  0px
Border:         1px solid #3D2800
Background:     #1A0F00
Padding:        20px
```

### Navigation
```
Height:         48px
Background:     #1A0F00
Border bottom:  1px solid #FFB000
```

---

## CSS / Component Examples

```css
/* CRTスクリーン効果 */
.crt-screen {
  position: relative;
  background: #1A0F00;
  border-radius: 20px / 16px;
  box-shadow: inset 0 0 60px rgba(255, 176, 0, 0.05);
  overflow: hidden;
}
.crt-screen::before {
  content: '';
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    0deg,
    transparent,
    transparent 2px,
    rgba(255, 176, 0, 0.03) 2px,
    rgba(255, 176, 0, 0.03) 4px
  );
  pointer-events: none;
}

/* フリッカーカーソル */
@keyframes blink {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
.cursor {
  display: inline-block;
  width: 10px;
  height: 18px;
  background: #FFB000;
  animation: blink 1s step-end infinite;
  box-shadow: 0 0 8px rgba(255, 176, 0, 0.6);
}

/* アンバーグローテキスト */
.amber-glow {
  color: #FFB000;
  text-shadow: 0 0 4px rgba(255, 176, 0, 0.4), 0 0 12px rgba(255, 176, 0, 0.2);
}
```

---

## Do's and Don'ts

### Do
- 全テキストをmonospaceに
- スキャンライン効果でCRT感を出す
- テキストにアンバーのグローシャドウ

### Don't
- サンセリフ/セリフフォントを使わない
- 角丸を使わない（CRT画面の角丸のみ例外）
- 明るい背景にしない

---

*Design Style: Amber Terminal — 2026-04-10*
