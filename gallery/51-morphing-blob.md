# DESIGN.md — 51. モーフィングブロブ

> 有機的にうねるblob shapeが空間を支配するデザインシステム。  
> すべてのUIパーツが丸く、柔らかく、生き物のように変形し続ける。

---

## Project Overview

- **Project Name**: Morphing Blob UI
- **Vibe**: "生命体のように脈打つ有機的フォルム。柔らかさの中に未来を感じる"
- **Target User**: クリエイティブスタジオ、アート系サービス、子ども向け教育アプリのユーザー

---

## Color Palette & Roles

```
Primary:      #8B5CF6   （メインCTA・ブロブのアクセントカラー）
Secondary:    #A78BFA   （サブアクション・ホバー時のブロブカラー）
Background:   #FEFCE8   （温かみのあるクリームイエロー背景）
Surface:      #FEF9C3   （カード背景・ブロブ内のコンテンツ領域）
Text:         #1C1917   （本文テキスト）
Text-muted:   #78716C   （補足テキスト・キャプション）
Accent:       #F97316   （警告・通知バッジ）
Border:       #E7E5E4   （区切り線・薄い枠線）
```

**コントラスト比の必須要件**
- Body text（#1C1917 on #FEFCE8）: 4.5:1 以上（WCAG AA）
- Large text・見出し: 3:1 以上（WCAG AA）

---

## Typography Rules

```
Font:          "Zen Maru Gothic", sans-serif
Font-en:       "Nunito", sans-serif
Base size:     16px
Line height:   1.8
Letter spacing: 0.03em

Heading weights:
  H1: Bold（700）、36px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

---

## Component Stylings

### Button
```
Border radius:  9999px（完全な楕円形・ピル型）
Padding:        14px 32px
Min width:      140px
Font weight:    Bold（700）
Font size:      16px

Primary button:
  background: #8B5CF6
  color: #FFFFFF
  border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%（静止時のブロブ形状）
  transition: border-radius 0.8s ease-in-out

Secondary button:
  background: transparent
  border: 2px solid #8B5CF6
  color: #8B5CF6
  border-radius: 9999px
```

### Card
```
Border radius:  30% 70% 70% 30% / 30% 30% 70% 70%（ブロブ形状）
Padding:        32px
Border:         none
Shadow:         0 8px 32px rgba(139, 92, 246, 0.15)
Background:     #FEF9C3
Animation:      morph 8s ease-in-out infinite（常にゆっくり変形）
```

### Input / Form
```
Border radius:  9999px
Border:         2px solid #E7E5E4
Padding:        12px 20px
Font size:      16px
Focus outline:  2px solid #8B5CF6
Focus border-radius: blob形状にモーフィング
```

### Navigation
```
Height:         72px
Background:     rgba(254, 252, 232, 0.8) + backdrop-filter: blur(12px)
Logo width:     100px
Link spacing:   28px
Border radius:  ナビ全体をブロブ形状にする
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    64px（モバイルは 20px）
Section spacing:  120px（ブロブの余白を考慮し大きめ）
Grid columns:     12
Gutter:           40px（ブロブ同士が重ならないよう広め）
```

---

## Do's and Don'ts

### Do
- すべてのカード・ボタンにブロブ形状の `border-radius` を適用する
- アニメーションは `ease-in-out` で有機的に
- ブロブ同士は少しだけ重なるようにレイアウトする
- 背景にも大きなブロブを装飾として配置する

### Don't
- 直角（`border-radius: 0`）を使わない
- アニメーションの速度を 0.3s 以下にしない（急すぎると有機感が消える）
- ブロブの色にパレット外の色を使わない
- 細い直線のボーダーを多用しない

---

## CSS / Component Examples

### ブロブモーフィングアニメーション

```css
@keyframes morph {
  0% {
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
  }
  25% {
    border-radius: 58% 42% 56% 44% / 34% 68% 32% 66%;
  }
  50% {
    border-radius: 50% 50% 34% 66% / 56% 68% 32% 44%;
  }
  75% {
    border-radius: 42% 58% 64% 36% / 48% 32% 68% 52%;
  }
  100% {
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
  }
}
```

### ブロブカードスタイル

```css
.blob-card {
  width: 320px;
  padding: 32px;
  background: #FEF9C3;
  border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
  box-shadow: 0 8px 32px rgba(139, 92, 246, 0.15);
  animation: morph 8s ease-in-out infinite;
  transition: transform 0.6s ease-in-out;
}

.blob-card:hover {
  transform: scale(1.05);
  box-shadow: 0 12px 48px rgba(139, 92, 246, 0.25);
}
```

### 背景装飾ブロブ

```css
.blob-decoration {
  position: absolute;
  width: 400px;
  height: 400px;
  background: linear-gradient(135deg, #8B5CF6 0%, #A78BFA 100%);
  border-radius: 58% 42% 56% 44% / 34% 68% 32% 66%;
  opacity: 0.12;
  animation: morph 12s ease-in-out infinite;
  z-index: -1;
  filter: blur(40px);
}
```

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
