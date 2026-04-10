# DESIGN.md — 60. ホログラフィック

> 虹色の光沢が角度によって変わるホログラム効果。  
> トレーディングカードのレアカードのような、見る角度で表情を変えるUI。

---

## Project Overview

- **Project Name**: Holographic UI
- **Vibe**: "光のプリズムが踊る、触れるたびに表情を変えるホログラフィックな世界"
- **Target User**: NFT・デジタルコレクタブル、ファッションEC、プレミアム会員向けサービス

---

## Color Palette & Roles

```
Primary:      #C084FC   （ソフトパープル・メインCTA）
Secondary:    #67E8F9   （シアン・サブアクション）
Background:   #18181B   （ジンクダーク・深い黒背景）
Surface:      #27272A   （カード背景・やや明るいダーク）
Text:         #FAFAFA   （テキスト・ほぼ白）
Text-muted:   #A1A1AA   （補足テキスト・グレー）
Accent:       #FDE68A   （ゴールドイエロー・ハイライト）
Border:       rgba(255, 255, 255, 0.1)   （薄いボーダー）
Holo-gradient: linear-gradient(135deg, #C084FC, #67E8F9, #FDE68A, #F472B6, #C084FC)
```

**コントラスト比の必須要件**
- Body text（#FAFAFA on #18181B）: 17.4:1（WCAG AAA）
- Text-muted（#A1A1AA on #18181B）: 5.8:1（WCAG AA）

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", sans-serif
Base size:     15px
Line height:   1.7
Letter spacing: 0.02em

Heading weights:
  H1: Bold（700）、38px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、15px
Small: Regular（400）、13px
Caption: Regular（400）、11px
```

---

## Component Stylings

### Button
```
Border radius:  10px
Padding:        12px 28px
Min width:      130px
Font weight:    SemiBold（600）
Font size:      15px

Primary button:
  background: linear-gradient(135deg, #C084FC, #67E8F9)
  color: #18181B
  position: relative
  ※ ホログラフィックシマーオーバーレイ付き

Secondary button:
  background: transparent
  border: 1px solid rgba(192, 132, 252, 0.5)
  color: #C084FC
```

### Card
```
Border radius:  16px
Padding:        24px
Border:         1px solid rgba(255, 255, 255, 0.1)
Shadow:         0 8px 32px rgba(0, 0, 0, 0.4)
Background:     #27272A
※ ホバー時にホログラフィックグラデーションが走る
```

### Input / Form
```
Border radius:  8px
Border:         1px solid rgba(255, 255, 255, 0.15)
Padding:        10px 14px
Font size:      15px
Background:     #18181B
Color:          #FAFAFA
Focus:          border-image: linear-gradient(135deg, #C084FC, #67E8F9) 1
```

### Navigation
```
Height:         64px
Background:     rgba(24, 24, 27, 0.9) + backdrop-filter: blur(16px)
Logo width:     110px
Link spacing:   32px
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    64px（モバイルは 20px）
Section spacing:  96px
Grid columns:     12
Gutter:           24px
```

---

## Do's and Don'ts

### Do
- ホログラフィックエフェクトはカード・ボタン・バッジに限定
- マウス位置に連動してグラデーション角度を変える
- 控えめなシマーアニメーション（2〜4秒サイクル）
- 特別な要素（プレミアム・レア等）にのみホロ効果を強く適用

### Don't
- 全要素にホロ効果を適用しない（特別感が薄れる）
- テキスト本体にホログラデーションを使わない（可読性低下）
- 明るい背景でホロ効果を使わない（ダーク背景で映える）
- アニメーション速度を 1s 以下にしない（落ち着きを保つ）

---

## CSS / Component Examples

### ホログラフィックグラデーション

```css
.holo-surface {
  position: relative;
  background: #27272A;
  border-radius: 16px;
  padding: 24px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.holo-surface::before {
  content: "";
  position: absolute;
  inset: 0;
  background: linear-gradient(
    135deg,
    rgba(192, 132, 252, 0.15) 0%,
    rgba(103, 232, 249, 0.15) 25%,
    rgba(253, 230, 138, 0.15) 50%,
    rgba(244, 114, 182, 0.15) 75%,
    rgba(192, 132, 252, 0.15) 100%
  );
  background-size: 200% 200%;
  opacity: 0;
  transition: opacity 0.5s ease;
  pointer-events: none;
}

.holo-surface:hover::before {
  opacity: 1;
  animation: holo-shift 3s ease infinite;
}

@keyframes holo-shift {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
```

### シマーアニメーション

```css
.shimmer-card {
  position: relative;
  background: #27272A;
  border-radius: 16px;
  padding: 32px;
  overflow: hidden;
}

.shimmer-card::after {
  content: "";
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(
    45deg,
    transparent 30%,
    rgba(255, 255, 255, 0.05) 40%,
    rgba(255, 255, 255, 0.12) 50%,
    rgba(255, 255, 255, 0.05) 60%,
    transparent 70%
  );
  transform: rotate(0deg);
  animation: shimmer 4s ease-in-out infinite;
  pointer-events: none;
}

@keyframes shimmer {
  0% { transform: translateX(-100%) rotate(25deg); }
  100% { transform: translateX(100%) rotate(25deg); }
}
```

### ホログラフィックバッジ

```css
.holo-badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 16px;
  border-radius: 9999px;
  font-size: 13px;
  font-weight: 600;
  color: #18181B;
  background: linear-gradient(
    135deg,
    #C084FC 0%,
    #67E8F9 33%,
    #FDE68A 66%,
    #F472B6 100%
  );
  background-size: 300% 300%;
  animation: holo-badge-shift 4s ease infinite;
  box-shadow:
    0 0 12px rgba(192, 132, 252, 0.3),
    0 0 24px rgba(103, 232, 249, 0.15);
}

@keyframes holo-badge-shift {
  0% { background-position: 0% 50%; }
  33% { background-position: 100% 0%; }
  66% { background-position: 50% 100%; }
  100% { background-position: 0% 50%; }
}
```

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
