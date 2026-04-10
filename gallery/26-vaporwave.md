# DESIGN.md — ヴェイパーウェイブ

---

## Project Overview

- **Project Name**: Vaporwave Portal
- **Vibe**: "80〜90年代のネット文化を再解釈した退廃的サイバー美学。紫×ピンク×シアンのグラデーションが織りなすデジタルノスタルジア"
- **Target User**: レトロフューチャー・ネットカルチャー愛好家、20〜30代のクリエイター

---

## Color Palette & Roles

```
Primary:      #FF71CE   （メインCTA・ネオンピンクのアクセント）
Secondary:    #B967FF   （サブアクション・タグ・紫のグラデーション起点）
Background:   #1A0A2E   （ページ背景。深い紫のダークベース）
Surface:      #2D1B4E   （カード・セクション背景。やや明るい紫）
Text:         #E0D7FF   （本文テキスト。ラベンダー系の明るいトーン）
Text-muted:   #9B8FC2   （補足テキスト・キャプション）
Accent:       #01CDFE   （強調・シアンのネオングロー）
Border:       #3D2B6B   （区切り線・枠線。紫系のボーダー）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #E0D7FF on #1A0A2E ≈ 10.2:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "VT323", monospace
Font-en:       "VT323", monospace
Base size:     16px
Line height:   1.7
Letter spacing: 0.04em

Heading weights:
  H1: Regular（400）、36px ※VT323は単一ウェイト
  H2: Regular（400）、28px
  H3: Regular（400）、22px
  H4: Regular（400）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**ネオングロー効果（見出し用）**
```css
text-shadow:
  0 0 7px #FF71CE,
  0 0 10px #FF71CE,
  0 0 21px #FF71CE,
  0 0 42px #B967FF;
```

---

## Component Stylings

### Button
```
Border radius:  0px（シャープなエッジ、レトロ感）
Padding:        14px 28px
Min width:      140px
Font weight:    Regular（400）※VT323
Font size:      18px
Text transform: uppercase

Primary button:
  background: linear-gradient(135deg, #FF71CE, #B967FF)
  color: #FFFFFF
  box-shadow: 0 0 15px rgba(255, 113, 206, 0.5), 0 0 30px rgba(255, 113, 206, 0.2)
  border: none

Secondary button:
  background: transparent
  border: 2px solid #01CDFE
  color: #01CDFE
  box-shadow: 0 0 10px rgba(1, 205, 254, 0.3)

Hover:
  box-shadow intensity +50%
  グリッチアニメーション（transform: skew）を0.1秒適用
```

### Card
```
Border radius:  0px（シャープ・レトロ）
Padding:        24px
Border:         1px solid #3D2B6B
Background:     #2D1B4E
Shadow:         0 0 20px rgba(185, 103, 255, 0.15)

Hover時:
  border-color: #FF71CE
  box-shadow: 0 0 25px rgba(255, 113, 206, 0.3)
```

### Input / Form
```
Border radius:  0px
Border:         2px solid #3D2B6B
Background:     #1A0A2E
Padding:        12px 16px
Font size:      16px
Color:          #E0D7FF
Focus outline:  2px solid #01CDFE
Focus shadow:   0 0 10px rgba(1, 205, 254, 0.4)
Placeholder:    #9B8FC2
```

### Navigation
```
Height:         60px
Background:     #1A0A2E（border-bottom: 1px solid #3D2B6B）
Logo:           ネオングロー付きテキストロゴ
Link spacing:   36px
Link color:     #E0D7FF
Link hover:     #FF71CE with text-shadow glow
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    64px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px
```

**グリッチ・デコレーション**
- セクション区切りにスキャンラインやグリッチエフェクトのCSS装飾を使用
- 背景にCRTモニター風のオーバーレイ（repeating-linear-gradient）を薄く敷く

---

## Do's and Don'ts

### Do
- ネオングロー（text-shadow, box-shadow）を見出しやCTAに積極的に使う
- 紫→ピンク→シアンのグラデーションをアクセントに使う
- VT323などモノスペース・ピクセルフォントで統一する
- グリッチアニメーションをホバーやトランジションに控えめに入れる
- スキャンライン・CRTオーバーレイで雰囲気を出す

### Don't
- 明るい白背景を使わない（ダークベースを維持）
- セリフ体や丸ゴシックを混ぜない
- グロー効果を全要素に付けすぎない（重要な要素に絞る）
- コントラスト比 4.5:1 を下回るテキストを置かない
- グリッチアニメーションを常時再生しない（ホバー・トリガー時のみ）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*

---

## CSS / Component Examples

```css
/* ネオングロー テキスト */
.neon-text {
  color: #FF71CE;
  text-shadow: 0 0 10px #FF71CE, 0 0 40px #FF71CE, 0 0 80px #FF71CE;
}

/* グリッチエフェクト */
@keyframes glitch {
  0% { transform: translate(0); }
  20% { transform: translate(-3px, 3px); }
  40% { transform: translate(3px, -3px); }
  60% { transform: translate(-2px, -2px); }
  80% { transform: translate(2px, 2px); }
  100% { transform: translate(0); }
}
.glitch { animation: glitch 0.3s infinite; }

/* スキャンライン背景 */
.scanlines::after {
  content: '';
  position: absolute;
  inset: 0;
  background: repeating-linear-gradient(
    0deg, transparent, transparent 2px, rgba(0,0,0,0.1) 2px, rgba(0,0,0,0.1) 4px
  );
  pointer-events: none;
}
```
