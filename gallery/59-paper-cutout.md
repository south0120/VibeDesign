# DESIGN.md — 59. ペーパーカットアウト

> 切り紙・コラージュ・ちぎり絵。紙の質感と影のレイヤーで奥行きを表現。  
> デジタルなのに手作り感あふれる、温かくて遊び心のあるUI。

---

## Project Overview

- **Project Name**: Paper Cutout UI
- **Vibe**: "ハサミとのりで作ったような手作り感。紙の重なりが生む素朴な立体感"
- **Target User**: 教育系サービス、ハンドメイドマーケット、子ども向けクリエイティブアプリ

---

## Color Palette & Roles

```
Primary:      #E74C3C   （クラフトレッド・メインCTA）
Secondary:    #3498DB   （ペーパーブルー・サブアクション）
Background:   #FDF6E3   （クラフト紙のようなウォームクリーム）
Surface:      #FFFFFF   （白い紙のカード）
Text:         #2C3E50   （インクのような深いネイビー）
Text-muted:   #7F8C8D   （薄いインク）
Accent:       #F39C12   （マスタードイエロー・バッジ）
Border:       none      （ボーダーの代わりに影で区切る）
```

**コントラスト比の必須要件**
- Body text（#2C3E50 on #FDF6E3）: 9.1:1（WCAG AAA）
- Primary（#E74C3C on #FDF6E3）: 4.6:1（WCAG AA）

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Patrick Hand", cursive（手書き風）
Base size:     16px
Line height:   1.8
Letter spacing: 0.02em

Heading weights:
  H1: Bold（700）、34px
  H2: Bold（700）、26px
  H3: SemiBold（600）、22px
  H4: Medium（500）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px

※ 英数字は手書き風フォントで温かみを出す
```

---

## Component Stylings

### Button
```
Border radius:  4px（紙っぽく最小限の丸み）
Padding:        12px 24px
Min width:      120px
Font weight:    Bold（700）
Font size:      16px
Transform:      rotate(-1deg)（微かに傾ける）

Primary button:
  background: #E74C3C
  color: #FFFFFF
  box-shadow: 3px 3px 0 rgba(0,0,0,0.15)（紙の影）

Secondary button:
  background: #FFFFFF
  border: 2px dashed #E74C3C（切り取り線風）
  color: #E74C3C
```

### Card
```
Border radius:  2px（紙の角）
Padding:        24px
Border:         none
Shadow:         2px 4px 8px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.08)（紙が浮いている影）
Background:     #FFFFFF
Transform:      rotate(random -2deg 〜 2deg)（カードごとに微妙に傾ける）
```

### Input / Form
```
Border radius:  2px
Border:         none / border-bottom: 2px solid #2C3E50
Padding:        10px 4px
Font size:      16px
Background:     transparent
Focus:          border-bottom: 2px solid #E74C3C
※ ノートの罫線風にする
```

### Navigation
```
Height:         72px
Background:     #FDF6E3
Logo:           手書き風のロゴテキスト
Link spacing:   32px
Border-bottom:  マスキングテープ風の装飾
```

---

## Layout Principles

```
Max width:        1000px
Outer padding:    60px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           28px

※ 要素を完全に整列させず、微かにずらして「手で置いた」感を出す
```

---

## Do's and Don'ts

### Do
- カードは微かに傾ける（`rotate(-2deg)` 〜 `rotate(2deg)`）
- 影は複数レイヤーで「紙の重なり」を表現
- 切り取り線（`border: dashed`）を装飾に使う
- 角がちぎれたようなエッジ処理を加える

### Don't
- 完璧に整列させない（少しの不揃いが命）
- グラデーション背景を使わない（フラットな紙の色）
- 金属的・ガラス的なエフェクトを使わない
- ドロップシャドウを `blur` 20px 以上にしない

---

## CSS / Component Examples

### レイヤードペーパーシャドウ

```css
.paper-card {
  position: relative;
  background: #FFFFFF;
  padding: 24px;
  border-radius: 2px;
  transform: rotate(-1deg);
  box-shadow:
    1px 2px 4px rgba(0, 0, 0, 0.1),
    0 1px 2px rgba(0, 0, 0, 0.06);
}

/* 背後に重なる紙のレイヤー */
.paper-card::before {
  content: "";
  position: absolute;
  inset: 4px -3px -6px 3px;
  background: #F0E6D3;
  border-radius: 2px;
  z-index: -1;
  transform: rotate(1.5deg);
  box-shadow: 1px 2px 4px rgba(0, 0, 0, 0.08);
}

.paper-card::after {
  content: "";
  position: absolute;
  inset: 8px -6px -10px 6px;
  background: #E8DCC8;
  border-radius: 2px;
  z-index: -2;
  transform: rotate(-2deg);
  box-shadow: 1px 2px 4px rgba(0, 0, 0, 0.06);
}
```

### ちぎれたエッジ（Torn Edge Border）

```css
.torn-edge {
  position: relative;
  background: #FFFFFF;
  padding: 32px;
  margin-bottom: 40px;
}

.torn-edge::after {
  content: "";
  position: absolute;
  bottom: -20px;
  left: 0;
  right: 0;
  height: 20px;
  background-image:
    url("data:image/svg+xml,%3Csvg viewBox='0 0 1200 20' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0,10 Q30,0 60,8 T120,12 T180,6 T240,10 T300,4 T360,12 T420,8 T480,10 T540,6 T600,14 T660,8 T720,10 T780,4 T840,12 T900,8 T960,10 T1020,6 T1080,12 T1140,8 T1200,10 L1200,20 L0,20 Z' fill='%23FFFFFF'/%3E%3C/svg%3E");
  background-size: 100% 100%;
}

/* 上部のちぎれたエッジ */
.torn-edge::before {
  content: "";
  position: absolute;
  top: -20px;
  left: 0;
  right: 0;
  height: 20px;
  background-image:
    url("data:image/svg+xml,%3Csvg viewBox='0 0 1200 20' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0,10 Q30,20 60,12 T120,8 T180,14 T240,10 T300,16 T360,8 T420,12 T480,10 T540,14 T600,6 T660,12 T720,10 T780,16 T840,8 T900,12 T960,10 T1020,14 T1080,8 T1140,12 T1200,10 L1200,0 L0,0 Z' fill='%23FFFFFF'/%3E%3C/svg%3E");
  background-size: 100% 100%;
}
```

### マスキングテープ装飾

```css
.masking-tape {
  position: relative;
  display: inline-block;
}

.masking-tape::before {
  content: "";
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%) rotate(-2deg);
  width: 80px;
  height: 24px;
  background: rgba(243, 156, 18, 0.6);
  border-left: 1px dashed rgba(0, 0, 0, 0.1);
  border-right: 1px dashed rgba(0, 0, 0, 0.1);
}
```

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
