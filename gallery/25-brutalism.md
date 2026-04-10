# DESIGN.md — ブルータリズム

> 生々しく大胆なデザインシステム。太いボーダー、モノスペースフォント、  
> オフセットシャドウでぶつ切り感のある力強いレイアウトを構築する。

---

## Project Overview

- **Project Name**: ブルータリズムデザイン
- **Vibe**: "生々しく、大胆で、媚びない。構造そのものが装飾であるような、力強いビジュアル"
- **Target User**: クリエイティブエージェンシー、実験的なポートフォリオ、アート系プロジェクト

---

## Color Palette & Roles

```
Primary:      #FF0000   （メインCTA・リンク・ブランドカラー。原色レッド）
Secondary:    #0000FF   （サブアクション・タグ。原色ブルー）
Background:   #FFFFFF   （ページ背景。純白）
Surface:      #FFFF00   （カード・セクション背景。原色イエロー）
Text:         #000000   （本文テキスト。真黒）
Text-muted:   #555555   （補足テキスト・キャプション）
Accent:       #0000FF   （強調・バッジ。原色ブルー）
Border:       #000000   （区切り線・枠線。太い黒ボーダー）
```

**コントラスト比の必須要件**
- Body text（#000000 on #FFFFFF）: 21:1（最大値。WCAG AAA適合）
- Text on Surface（#000000 on #FFFF00）: 約 19.6:1（WCAG AAA適合）
- 確認ツール: https://webaim.org/resources/contrastchecker/

**注意**: #FF0000 on #FFFFFF は約 4.0:1。大きいテキスト（18px Bold以上）でのみ使用すること。

---

## Typography Rules

```
Font:          "Space Mono", monospace
Font-ja:       "Noto Sans Mono CJK JP", "Noto Sans JP", monospace
Base size:     16px
Line height:   1.6
Letter spacing: 0em

Heading weights:
  H1: Bold（700）、48px（大きく、衝撃的に）
  H2: Bold（700）、36px
  H3: Bold（700）、24px
  H4: Bold（700）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

**スタイルノート**
- モノスペースフォントを全面的に使い、コード的・工業的な印象を出す
- 見出しは全て Bold。ウェイトの段階を減らし、サイズ差で階層を示す
- text-transform: uppercase を英語見出しに積極的に適用
- H1 は他のスタイルより極端に大きく設定（48px以上も可）

---

## Component Stylings

### Button
```
Border radius:  0px（角丸なし。完全にシャープ）
Padding:        16px 32px
Min width:      140px
Font weight:    Bold（700）
Font size:      16px
Font family:    "Space Mono", monospace
Text transform: uppercase
Letter spacing: 0.05em

Primary button:
  background: #FF0000
  color: #FFFFFF
  border: 3px solid #000000
  box-shadow: 4px 4px 0px #000000
  hover → transform: translate(-2px, -2px), box-shadow: 6px 6px 0px #000000
  active → transform: translate(4px, 4px), box-shadow: 0px 0px 0px #000000
  transition: all 0.1s ease（素早い反応）

Secondary button:
  background: #FFFFFF
  color: #000000
  border: 3px solid #000000
  box-shadow: 4px 4px 0px #000000
  hover → background: #FFFF00

Accent button:
  background: #0000FF
  color: #FFFFFF
  border: 3px solid #000000
  box-shadow: 4px 4px 0px #000000
```

### Card
```
Border radius:  0px（角丸なし）
Padding:        24px
Border:         3px solid #000000
Background:     #FFFFFF
Shadow:         4px 4px 0px #000000（ハードなオフセットシャドウ）

バリエーション:
  Surface card: background #FFFF00, border 3px solid #000000
  Accent card:  background #FF0000, color #FFFFFF, border 3px solid #000000

ホバー時:
  transform: translate(-2px, -2px)
  box-shadow: 6px 6px 0px #000000
  transition: all 0.1s ease
```

### Input / Form
```
Border radius:  0px
Border:         3px solid #000000
Padding:        12px 16px
Font size:      16px
Font family:    "Space Mono", monospace
Background:     #FFFFFF
Focus:
  outline: none
  box-shadow: 4px 4px 0px #000000
  border-color: #FF0000
Placeholder:    color #555555, text-transform: uppercase
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Border-bottom:  3px solid #000000
Logo width:     140px
Link spacing:   28px
Link style:     color: #000000, font-weight: 700, text-transform: uppercase,
                font-family: "Space Mono", letter-spacing: 0.05em
Hover:          background: #FFFF00（リンク部分にベタ塗りハイライト）
Active:         background: #FF0000, color: #FFFFFF
```

---

## Layout Principles

```
Max width:        1400px（ブルータリズムは広めのキャンバスを活かす）
Outer padding:    48px（モバイルは 16px）
Section spacing:  64px（セクション間は border-top: 3px solid #000 で区切る）
Grid columns:     12（ただし非対称レイアウトを積極的に使う）
Gutter:           24px

特記事項:
- グリッドは必ずしも均等に割らない。7:5、8:4 など非対称を活用
- セクション区切りにはボーダーを使う（余白だけで区切らない）
- テキストを極端に大きく配置してタイポグラフィ自体を装飾にする
- 色面をぶつ切りに配置し、背景色を大胆に切り替える
- アニメーションは最小限。使う場合は即座に反応する 0.1s ease
- 画像はグレースケールフィルター（filter: grayscale(100%)）を適用する
  ホバーで色を戻す（filter: grayscale(0%)、transition: 0.3s）
```

---

## Do's and Don'ts

### Do
- border: 3px solid #000000 をあらゆる要素に一貫して使う
- box-shadow は 4px 4px 0px #000000 のハードオフセットのみ使う
- モノスペースフォント（Space Mono）を全面的に使う
- 原色（赤・青・黄・白・黒）のみで構成する
- text-transform: uppercase を英語テキストに適用する
- 非対称なレイアウトとぶつ切りの色面で構成する

### Don't
- 角丸（border-radius）を一切使わない
- ぼかし付きのシャドウ（blur > 0）を使わない
- パステルカラーや淡い色を使わない（原色のみ）
- セリフフォントやサンセリフフォントを混ぜない（モノスペースのみ）
- ease-in-out の緩やかなアニメーションを使わない（即座に反応させる）
- コンテンツを中央揃えに統一しない（左寄せ・非対称を基本とする）
- コントラスト比 4.5:1 を下回るテキストを置かない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
