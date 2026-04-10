# DESIGN.md — サイバーパンク

---

## Project Overview

- **Project Name**: Cyberpunk HUD
- **Vibe**: "ネオンが煌めくダークな未来都市。ターミナル風HUDインターフェースで、情報を冷徹に可視化する"
- **Target User**: テック系プロフェッショナル、SF・サイバーパンク愛好家、ハッカーカルチャーに親しむ20〜40代

---

## Color Palette & Roles

```
Primary:      #00FF41   （メインCTA・マトリックスグリーン）
Secondary:    #00D4FF   （サブアクション・サイバーブルー）
Background:   #0A0A0A   （ページ背景。ほぼ真っ黒）
Surface:      #111111   （カード・セクション背景。わずかに明るいブラック）
Text:         #00FF41   （本文テキスト。グリーンのターミナル文字）
Text-muted:   #00AA2A   （補足テキスト。暗めのグリーン）
Accent:       #FF0090   （強調・ネオンマゼンタ。警告・重要アクション）
Border:       #1A1A1A   （区切り線・枠線。暗いグレー。グロー時に変化）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #00FF41 on #0A0A0A ≈ 12.3:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

**ネオンカラーバリエーション**
```
ネオングリーン:   #00FF41
ネオンマゼンタ:   #FF0090
ネオンシアン:     #00D4FF
ネオンイエロー:   #FFE400
```

---

## Typography Rules

```
Font:          "JetBrains Mono", monospace
Font-en:       "JetBrains Mono", monospace
Base size:     15px
Line height:   1.6
Letter spacing: 0.02em

Heading weights:
  H1: Bold（700）、32px
  H2: Bold（700）、24px
  H3: Medium（500）、20px
  H4: Medium（500）、17px

Body: Regular（400）、15px
Small: Regular（400）、13px
Caption: Light（300）、11px
```

**ネオングロー効果（見出し・重要テキスト用）**
```css
/* グリーングロー */
text-shadow:
  0 0 7px #00FF41,
  0 0 10px #00FF41,
  0 0 21px #00FF41;

/* マゼンタグロー */
text-shadow:
  0 0 7px #FF0090,
  0 0 10px #FF0090,
  0 0 21px #FF0090;
```

---

## Component Stylings

### Button
```
Border radius:  2px（ほぼシャープ。HUD感）
Padding:        12px 24px
Min width:      140px
Font weight:    Bold（700）
Font size:      14px
Text transform: uppercase
Letter spacing: 0.1em

Primary button:
  background: transparent
  color: #00FF41
  border: 1px solid #00FF41
  box-shadow: 0 0 10px rgba(0, 255, 65, 0.3), inset 0 0 10px rgba(0, 255, 65, 0.1)

Accent button:
  background: transparent
  color: #FF0090
  border: 1px solid #FF0090
  box-shadow: 0 0 10px rgba(255, 0, 144, 0.3), inset 0 0 10px rgba(255, 0, 144, 0.1)

Filled button:
  background: #00FF41
  color: #0A0A0A
  border: none
  box-shadow: 0 0 15px rgba(0, 255, 65, 0.4)

Hover:
  box-shadow intensity +80%
  background: rgba(0, 255, 65, 0.1)（outline系の場合）
  transition: all 0.15s ease
```

### Card
```
Border radius:  2px
Padding:        24px
Border:         1px solid #1A1A1A
Background:     #111111
Shadow:         none（デフォルト）

Hover時:
  border-color: #00FF41
  box-shadow: 0 0 15px rgba(0, 255, 65, 0.15)

HUD装飾:
  カード左上・右下にコーナーブラケット装飾（疑似要素で L字型の線）
  border-color を #00FF41 にしてグロー
```

### Input / Form
```
Border radius:  2px
Border:         1px solid #1A1A1A
Background:     #0A0A0A
Padding:        10px 14px
Font size:      15px
Color:          #00FF41
Focus outline:  1px solid #00FF41
Focus shadow:   0 0 10px rgba(0, 255, 65, 0.3)
Placeholder:    #00AA2A
Caret color:    #00FF41
```

### Navigation
```
Height:         56px
Background:     #0A0A0A（border-bottom: 1px solid #1A1A1A）
Logo:           モノスペースのテキストロゴ。グリーングロー付き
Link spacing:   32px
Link color:     #00FF41
Link hover:     #FF0090 with glow
Font weight:    Medium（500）
Text transform: uppercase
Font size:      13px
Letter spacing: 0.08em
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    64px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px
```

**HUD・サイバーパンク装飾**
- スキャンライン効果: `background: repeating-linear-gradient(0deg, transparent, transparent 2px, rgba(0,255,65,0.03) 2px, rgba(0,255,65,0.03) 4px)` をオーバーレイ
- セクション区切りに点線（border-style: dashed）またはグリッドライン風の装飾
- データ表示はテーブル・グリッドで構造化し、ターミナル風のモノスペース表示
- アニメーションは控えめなスキャンライン・タイプライター効果

---

## Do's and Don'ts

### Do
- ネオングロー（text-shadow, box-shadow）をCTAや見出しに使う
- JetBrains Monoなどモノスペースフォントで統一しターミナル感を出す
- ボーダーは細め（1px）でグロー効果と組み合わせる
- HUD風のコーナーブラケットや照準風の装飾を取り入れる
- スキャンラインオーバーレイで雰囲気を強化する

### Don't
- 明るい白背景を使わない（ダークベースを維持）
- 丸ゴシックやセリフ体を使わない
- パステルカラーや淡い色を使わない
- コントラスト比 4.5:1 を下回るテキストを置かない
- グロー効果を全要素に付けすぎない（視認性を損なう）
- アニメーションを常時再生し続けない（パフォーマンスに配慮）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
