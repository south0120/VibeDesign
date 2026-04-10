# DESIGN.md — 54. スプリットスクリーン

> 画面を真っ二つに分割。左右で完全に異なるスタイル・色・世界観がぶつかり合う。  
> 対比の力でメッセージを際立たせるダイナミックなレイアウト。

---

## Project Overview

- **Project Name**: Split Screen UI
- **Vibe**: "対立と調和。二つの世界が一つの画面で衝突するダイナミズム"
- **Target User**: ブランド比較サイト、ポートフォリオ、ビフォーアフター系コンテンツ

---

## Color Palette & Roles

```
Primary-Left:   #FF4757   （左側のメインカラー・ホットレッド）
Primary-Right:  #2ED573   （右側のメインカラー・ヴィヴィッドグリーン）
Background-L:   #FFF5F5   （左側の薄いピンク背景）
Background-R:   #F0FFF4   （右側の薄いグリーン背景）
Surface:        #FFFFFF   （オーバーレイカード・共通領域）
Text:           #1A1A2E   （本文テキスト・両側共通）
Text-muted:     #6B7280   （補足テキスト）
Accent:         #FFC312   （共通アクセント・CTA強調）
Border:         #E5E7EB   （区切り線・カード枠）
```

**コントラスト比の必須要件**
- Body text（#1A1A2E on #FFF5F5 / #F0FFF4）: 4.5:1 以上
- Primary colors: ボタン上の白文字で 4.5:1 以上を確保

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "DM Sans", sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0.01em

Heading weights:
  H1: Black（900）、42px
  H2: Bold（700）、30px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px

※ 左右で同じフォントを使い、色とウェイトで差をつける
```

---

## Component Stylings

### Button
```
Border radius:  8px
Padding:        14px 32px
Min width:      140px
Font weight:    Bold（700）
Font size:      16px

Left-side button:
  background: #FF4757
  color: #FFFFFF

Right-side button:
  background: #2ED573
  color: #FFFFFF

Center CTA button:
  background: #FFC312
  color: #1A1A2E
```

### Card
```
Border radius:  12px
Padding:        24px
Border:         1px solid #E5E7EB
Shadow:         0 4px 20px rgba(0, 0, 0, 0.08)
Background:     #FFFFFF
※ 分割線をまたぐカードは両側の色をグラデーションで融合
```

### Input / Form
```
Border radius:  8px
Border:         1px solid #E5E7EB
Padding:        12px 16px
Font size:      16px
Focus outline:  2px solid（配置側のPrimaryカラー）
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Logo width:     130px
Link spacing:   36px
※ ナビバーは分割せず中立の白背景
```

---

## Layout Principles

```
Max width:        100vw（フルブリード）
Outer padding:    0px（分割画面は端から端まで）
Section spacing:  0px（セクション同士は密着）
Grid columns:     2（50/50分割が基本）
Gutter:           0px（分割線で区切る）

モバイル: 上下分割に切り替え（左→上、右→下）
```

---

## Do's and Don'ts

### Do
- 左右で明確にスタイルを分ける（色・写真のトーン等）
- 分割線は1pxの実線またはカラーグラデーション
- 中央にまたがる要素（CTA・ロゴ）で統一感を出す
- ホバーで分割比率がスライドするインタラクション

### Don't
- 左右の色を混ぜて中間色を作らない
- 3分割以上にしない（2分割の力を活かす）
- モバイルで左右分割を維持しない（上下に切り替える）
- 分割線を太くしすぎない（2px以下推奨）

---

## CSS / Component Examples

### 50/50スプリットレイアウト

```css
.split-screen {
  display: grid;
  grid-template-columns: 1fr 1fr;
  min-height: 100vh;
  width: 100%;
}

.split-left {
  background: #FFF5F5;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 64px 48px;
  border-right: 1px solid #E5E7EB;
}

.split-right {
  background: #F0FFF4;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 64px 48px;
}

@media (max-width: 768px) {
  .split-screen {
    grid-template-columns: 1fr;
    grid-template-rows: 1fr 1fr;
  }
  .split-left {
    border-right: none;
    border-bottom: 1px solid #E5E7EB;
  }
}
```

### コントラストカードスタイル

```css
.split-left .contrast-card {
  background: #FF4757;
  color: #FFFFFF;
  padding: 32px;
  border-radius: 12px;
  box-shadow: 0 8px 24px rgba(255, 71, 87, 0.3);
  transition: transform 0.3s ease;
}

.split-right .contrast-card {
  background: #2ED573;
  color: #FFFFFF;
  padding: 32px;
  border-radius: 12px;
  box-shadow: 0 8px 24px rgba(46, 213, 115, 0.3);
  transition: transform 0.3s ease;
}

.contrast-card:hover {
  transform: translateY(-4px) scale(1.02);
}
```

### スライド分割インタラクション

```css
.split-interactive {
  display: grid;
  grid-template-columns: 1fr 1fr;
  transition: grid-template-columns 0.5s cubic-bezier(0.25, 1, 0.5, 1);
}

.split-interactive:has(.split-left:hover) {
  grid-template-columns: 1.5fr 0.5fr;
}

.split-interactive:has(.split-right:hover) {
  grid-template-columns: 0.5fr 1.5fr;
}
```

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
