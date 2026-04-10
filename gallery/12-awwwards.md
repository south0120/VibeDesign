# DESIGN.md — Awwwards風デザインシステム

> エクスペリメンタルなデザインアワードサイト。境界を押し広げるクリエイティブ。

---

## Project Overview

- **Project Name**: AWWWARDS Experimental — 前衛的デザインアワードシステム
- **Vibe**: "デザインの常識を問い直す。タイポグラフィの実験、レイアウトの破壊と再構築が共存するエクスペリメンタル空間"
- **Target User**: 20〜40代のデジタルデザイナー、フロントエンドエンジニア、クリエイティブディレクター

---

## Color Palette & Roles

```
Primary:      #2D2D2D   （メインCTA・リンク。深いチャコール）
Secondary:    #7B7B7B   （サブアクション・タグ。ミドルグレー）
Background:   #F5F5F0   （ページ背景。温かみのあるオフホワイト）
Surface:      #EAEAE5   （カード・セクション背景。少し濃いオフホワイト）
Text:         #1A1A1A   （本文テキスト。ほぼ黒）
Text-muted:   #8A8A85   （補足テキスト・キャプション）
Accent:       #FF4D00   （強調・ホバー・受賞バッジ。ビビッドオレンジ）
Border:       #D5D5D0   （区切り線・枠線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #1A1A1A on #F5F5F0 = 15.2:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Space Grotesk", "Syne", sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: Black（900）、72px（大胆な見出しが特徴）
  H2: Bold（700）、48px
  H3: SemiBold（600）、28px
  H4: Medium（500）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Medium（500）、11px、text-transform: uppercase、letter-spacing: 0.12em

Display（特大見出し）:
  Font: "Space Grotesk"
  Weight: Black（900）
  Size: 96〜160px
  Line height: 0.9
  Letter spacing: -0.04em（タイトに詰める）
```

**デザイン意図**: Awwwardsのようなサイトでは、タイポグラフィ自体がビジュアル要素。見出しを極端に大きくし、字間をタイトに詰めることでインパクトを出す。

---

## Component Stylings

### Button
```
Border radius:  100px（完全な丸ピル型）
Padding:        14px 36px
Min width:      160px
Font weight:    Medium（500）
Font size:      14px
Letter spacing: 0.06em
text-transform: uppercase

Primary button:
  background: #2D2D2D
  color: #F5F5F0
  transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1)
  hover: background #FF4D00, transform scale(1.02)

Secondary button:
  background: transparent
  border: 1.5px solid #2D2D2D
  color: #2D2D2D
  hover: background #2D2D2D, color #F5F5F0
```

### Card
```
Border radius:  16px
Padding:        28px
Border:         none
Shadow:         none
Background:     #EAEAE5
Hover:          transform translateY(-4px), transition 0.5s cubic-bezier(0.16, 1, 0.3, 1)

Thumbnail:
  Border radius: 12px
  Aspect ratio:  16:9
  Overflow:      hidden
  Hover:         img scale(1.05), transition 0.6s ease
```

### Input / Form
```
Border radius:  100px（ピル型で統一）
Border:         1.5px solid #D5D5D0
Padding:        14px 24px
Font size:      16px
Focus outline:  border-color #2D2D2D, box-shadow 0 0 0 3px rgba(45,45,45,0.1)
Background:     #FFFFFF
```

### Navigation
```
Height:         80px
Background:     transparent（スクロールで #F5F5F0 に変化）
Logo width:     100px
Link spacing:   36px
Font size:      13px
Font weight:    Medium（500）
Letter spacing: 0.08em
text-transform: uppercase
Backdrop-filter: blur(12px)（スクロール時）
```

### Badge / Tag
```
Border radius:  100px
Padding:        6px 16px
Font size:      11px
Font weight:    Medium（500）
Letter spacing: 0.1em
text-transform: uppercase
Background:     #2D2D2D
Color:          #F5F5F0
```

---

## Layout Principles

```
Max width:        1440px
Outer padding:    80px（モバイルは 20px）
Section spacing:  160px（セクション間は大胆に空ける）
Grid columns:     12
Gutter:           24px
```

**レイアウトの特徴**
- グリッドを意図的に崩す「ブロークングリッド」レイアウトを許容する
- テキストと画像のオーバーラップを積極的に使う
- スクロール連動のパララックスやリビールアニメーションを活用する
- 画面いっぱいのフルブリード画像セクションを挟む

---

## Do's and Don'ts

### Do
- Display サイズの見出しを大胆に使い、タイポグラフィをビジュアル要素として扱う
- ホバーアニメーションに cubic-bezier イージングを使い、動きに個性を持たせる
- 余白を極端に広く取り、呼吸感のあるレイアウトにする
- カーソルカスタマイズ（カスタムカーソル）で遊び心を出す
- uppercase + letter-spacing でキャプション・ラベルにリズムを作る

### Don't
- 装飾のためだけに色を増やさない。基本はモノトーン + Accent の 1 色
- 標準的なグリッドレイアウトだけで終わらせない（実験的な配置を恐れない）
- ストックフォトのような無個性な画像を使わない
- ボタンに角張ったデザインを使わない（ピル型で統一）
- ページ遷移を瞬時に行わない。トランジションで体験をつなげる
- アクセシビリティを犠牲にしない。実験的でも WCAG AA は守る

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
