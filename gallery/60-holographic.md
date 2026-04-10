# DESIGN.md — ホログラフィック

---

## Project Overview

- **Project Name**: ホログラフィック — 虹色のシマー
- **Vibe**: "角度で色が変わる虹色の光沢。ホログラムカードのような幻想的なプレミアム感"
- **Target User**: NFT・Web3、プレミアムブランド、テック企業

---

## Color Palette & Roles

```
Primary:      #C084FC   （メインCTA・パープル）
Secondary:    #38BDF8   （サブ・スカイブルー）
Background:   #18181B   （ページ背景・ジンクダーク）
Surface:      #27272A   （カード背景）
Text:         #FAFAFA   （本文テキスト）
Text-muted:   #71717A   （補足テキスト）
Accent:       #FB923C   （オレンジ・ハイライト）
Border:       #3F3F46   （ボーダー）
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

## CSS / Component Examples

```css
/* ホログラフィックカード */
.holo-card {
  background: #27272A;
  border-radius: 16px;
  padding: 32px;
  position: relative;
  overflow: hidden;
  border: 1px solid #3F3F46;
}
.holo-card::before {
  content: '';
  position: absolute;
  inset: -1px;
  border-radius: 16px;
  background: linear-gradient(
    135deg,
    #ff0080, #ff8c00, #40e0d0,
    #7b68ee, #ff0080, #ff8c00
  );
  background-size: 400% 400%;
  z-index: -1;
  opacity: 0;
  transition: opacity 0.5s;
  animation: holo-shift 6s ease infinite;
}
.holo-card:hover::before {
  opacity: 1;
}
@keyframes holo-shift {
  0%, 100% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
}

/* シマーエフェクト */
.shimmer {
  background: linear-gradient(
    110deg,
    transparent 25%,
    rgba(255, 255, 255, 0.1) 37%,
    transparent 63%
  );
  background-size: 200% 100%;
  animation: shimmer 2s infinite;
}
@keyframes shimmer {
  from { background-position: 200% 0; }
  to { background-position: -200% 0; }
}

/* ホログラフィックテキスト */
.holo-text {
  background: linear-gradient(
    90deg,
    #ff0080, #ff8c00, #40e0d0, #7b68ee, #ff0080
  );
  background-size: 200% auto;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  animation: holo-text-shift 4s linear infinite;
}
@keyframes holo-text-shift {
  from { background-position: 0% center; }
  to { background-position: 200% center; }
}

/* ホログラフィックボタン */
.holo-btn {
  background: linear-gradient(135deg, #C084FC, #38BDF8, #FB923C);
  background-size: 200% 200%;
  color: #18181B;
  font-weight: 600;
  border: none;
  border-radius: 12px;
  padding: 14px 32px;
  animation: holo-shift 4s ease infinite;
  transition: box-shadow 0.3s;
}
.holo-btn:hover {
  box-shadow: 0 0 24px rgba(192, 132, 252, 0.5);
}
```

---

## Do's and Don'ts

### Do
- ホバーでホログラフィック効果を見せる
- グラデーションのbackground-sizeをアニメーション
- シマー効果で光の流れを表現

### Don't
- 全要素をホログラフィックにしない（アクセントのみ）
- 背景を明るくしない（ダークだから光が映える）
- アニメーションを速くしすぎない（ゆっくり流す）

---

*Design Style: Holographic — 2026-04-10*
