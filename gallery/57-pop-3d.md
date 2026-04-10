# DESIGN.md — ポップ3D

---

## Project Overview

- **Project Name**: ポップ3D — 飛び出すカラフルUI
- **Vibe**: "太いカラフルなオフセットシャドウで立体感。おもちゃのような楽しさとポップさ"
- **Target User**: 子供向け、ゲーム、エンタメ、イベントサイト

---

## Color Palette & Roles

```
Primary:      #FF6B6B   （メインCTA・コーラル）
Secondary:    #4ECDC4   （サブ・ティール）
Background:   #FFFFFF   （ページ背景）
Surface:      #FFF5F5   （カード背景）
Text:         #1A1A1A   （本文テキスト）
Text-muted:   #888888   （補足テキスト）
Accent:       #FFE66D   （イエロー・バッジ）
Border:       #1A1A1A   （太いアウトライン）
```

---

## Typography Rules

```
Font:          "Quicksand", "Nunito", "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.6
H1: Bold 48px / H2: Bold 32px / H3: SemiBold 22px
```

---

## Component Stylings

### Button
```
Border radius:  16px
Padding:        16px 32px
Border:         3px solid #1A1A1A
Primary: background #FF6B6B, color #FFF
box-shadow: 6px 6px 0px #1A1A1A
Hover: transform translateY(-2px), box-shadow 8px 8px 0px #1A1A1A
Active: transform translateY(2px), box-shadow 2px 2px 0px #1A1A1A
```

### Card
```
Border radius:  20px
Padding:        28px
Border:         3px solid #1A1A1A
Background:     #FFFFFF
box-shadow:     8px 8px 0px #FF6B6B（カラーシャドウ）
Hover: box-shadow 8px 8px 0px #4ECDC4（色が変わる）
```

---

## CSS / Component Examples

```css
/* ポップ3Dカード */
.pop-card {
  background: #fff;
  border: 3px solid #1A1A1A;
  border-radius: 20px;
  padding: 28px;
  box-shadow: 8px 8px 0px #FF6B6B;
  transition: all 0.2s ease;
}
.pop-card:hover {
  transform: translateY(-4px);
  box-shadow: 12px 12px 0px #4ECDC4;
}

/* ポップ3Dボタン */
.pop-btn {
  background: #FF6B6B;
  color: #fff;
  border: 3px solid #1A1A1A;
  border-radius: 16px;
  padding: 16px 32px;
  font-weight: 700;
  box-shadow: 6px 6px 0px #1A1A1A;
  cursor: pointer;
  transition: all 0.15s ease;
}
.pop-btn:hover {
  transform: translateY(-2px);
  box-shadow: 8px 8px 0px #1A1A1A;
}
.pop-btn:active {
  transform: translateY(2px);
  box-shadow: 2px 2px 0px #1A1A1A;
}

/* バウンスアニメーション */
@keyframes bounce-in {
  0% { transform: scale(0.8); opacity: 0; }
  60% { transform: scale(1.05); }
  100% { transform: scale(1); opacity: 1; }
}
.pop-bounce { animation: bounce-in 0.5s cubic-bezier(0.68, -0.55, 0.27, 1.55); }
```

---

## Do's and Don'ts

### Do
- オフセットシャドウは必ず1色のソリッドカラーで
- ホバーで影の色を変えるインタラクション
- 太いボーダー（3px）を全要素に

### Don't
- ぼかしシャドウ（blur）を使わない
- 控えめな配色にしない
- 角丸を0にしない（16px以上でポップに）

---

*Design Style: Pop 3D — 2026-04-10*
