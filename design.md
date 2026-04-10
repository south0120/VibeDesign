# DESIGN.md — VibeDesign

---

## Project Overview

- **Project Name**: VibeDesign
- **Vibe**: "Appleのような引き算の美学。ミニマルで洗練された、プロダクトが主役になるデザイン"
- **Target User**: デザインシステムを活用して美しいWebを作りたいクリエイター・開発者

---

## Color Palette & Roles

```
Primary:      #0071E3   （メインCTA・リンク・ブランドカラー）
Secondary:    #AF52DE   （サブアクション・プロモーション・タグ）
Background:   #FFFFFF   （ページ背景）
Surface:      #F5F5F7   （カード・セクション背景）
Text:         #1D1D1F   （本文テキスト）
Text-muted:   #86868B   （補足テキスト・キャプション）
Accent:       #FF9500   （強調・警告・NEWバッジ）
Border:       #E8E8ED   （区切り線・枠線）
```

**ダークモード対応**
```
Background:   #000000
Surface:      #1D1D1F
Text:         #F5F5F7
Text-muted:   #424245
Primary:      #2997FF   （ダークでは明るいBlue）
Border:       #38383D
```

**追加アクセントカラー**
```
Blue Hover:   #0077ED   （ホバー状態）
Green:        #34C759   （成功・在庫あり・完了）
Red:          #FF3B30   （エラー・削除・緊急）
Teal:         #5AC8FA   （情報・ヒント）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）→ #1D1D1F on #FFFFFF = 15.4:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）→ #86868B on #FFFFFF = 3.5:1 ✓
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Hiragino Sans", "Hiragino Kaku Gothic ProN", "Yu Gothic", "Meiryo", sans-serif
Font-en:       -apple-system, BlinkMacSystemFont, "SF Pro Display", "Helvetica Neue", Arial, sans-serif
Font-mono:     "SF Mono", "Fira Code", Menlo, Consolas, monospace
Base size:     17px
Line height:   1.47
Letter spacing: 0.004em

Heading weights:
  H1: Bold（700）、96px  → Tablet: 72px / Mobile: 48px
  H2: SemiBold（600）、48px → Tablet: 40px / Mobile: 32px
  H3: SemiBold（600）、28px → Tablet: 24px / Mobile: 21px
  H4: SemiBold（600）、21px → Tablet: 19px / Mobile: 17px

Body: Regular（400）、17px（Desktop） / 17px（Mobile）
Small: Regular（400）、14px
Caption: Regular（400）、12px

Heading line heights:
  H1: 1.05
  H2: 1.08
  H3: 1.1
  Body: 1.47

Letter spacing by size:
  48px+:    -0.003em（詰める）
  28-40px:  0em（ニュートラル）
  17-21px:  0.004em - 0.011em（わずかに広げる）
```

---

## Component Stylings

### Button
```
Border radius:  980px（完全な丸角＝カプセル型）
Padding:        12px 28px（上下 左右）
Min width:      120px
Font weight:    Regular（400）
Font size:      17px
Letter spacing: 0.004em

Primary button:
  background: #0071E3
  color: #FFFFFF
  hover background: #0077ED

Secondary button:
  background: transparent
  border: 1px solid #424245
  color: #5AC8FA
  hover border: 1px solid #86868B
  hover color: #FFFFFF

Large button（CTA）:
  font-size: 21px
  padding: 16px 40px
```

### Card
```
Border radius:  20px
Padding:        48px
Background:     #1D1D1F（ダークカード）または #FFFFFF（ライトカード）
Border:         なし（ダークカード）/ 1px solid #E8E8ED（ライトカード）
Shadow:         なし（フラットデザイン）
Hover:          transform: scale(1.01)
```

### Input / Form
```
Border radius:  12px
Border:         1px solid #E8E8ED
Padding:        12px 16px
Font size:      17px
Focus outline:  2px solid #0071E3
Background:     #FFFFFF
```

### Navigation
```
Height:         48px
Background:     rgba(255, 255, 255, 0.72)
Backdrop:       saturate(180%) blur(20px)
Border bottom:  1px solid #E8E8ED
Logo size:      21px / SemiBold（600）
Link size:      12px / Regular（400）
Link spacing:   24px（リンク間の余白）
Position:       fixed top
z-index:        1000
```

---

## Layout Principles

```
Max width:        980px（コンテンツの最大幅）
Outer padding:    22px（左右余白。全デバイス共通の最低値）
Section spacing:  120px（Desktop） / 80px（Tablet） / 48px（Mobile）
Grid columns:     12（Desktop） / 6（Tablet） / 4（Mobile）
Gutter:           20px（Desktop・Tablet） / 16px（Mobile）

Spacing scale（8px grid）:
  --space-xs:   8px    （インライン要素の間隔）
  --space-sm:   16px   （ボタン内パディング）
  --space-md:   24px   （カード内パディング）
  --space-lg:   48px   （セクション内の要素間）
  --space-xl:   80px   （セクション間のマージン）
  --space-2xl:  120px  （ヒーロー上下のマージン）
  --space-3xl:  200px  （ページトップのヒーロー余白）

Breakpoints:
  Desktop:  > 1068px
  Tablet:   735px - 1068px
  Mobile:   < 735px
```

---

## Visual Hierarchy

```
Level 1 — Hero（96px Bold / ダーク背景 / 100vh）
           → ページの主役。スクロール前に目に入る

Level 2 — Section Title（48px SemiBold / センター揃え）
           → 各ブロックの入り口

Level 3 — Body + Subtitle（21-28px Regular-SemiBold）
           → 説明・詳細情報

Level 4 — CTA Link（17px Blue #0071E3）
           → "Learn more" "Buy" → 行動を促す

Level 5 — Nav + Footer（12-14px Gray #86868B）
           → 常に存在するが主張しない
```

---

## Imagery & Effects

```
Photography:
  背景:         純白 or 純黒。環境色なし
  ライティング:  均一で柔らかい光。影は最小限
  解像度:       Retina前提の2x / 3x画像

Effects:
  パララックス:   transform: translate3d()
  フェードイン:   opacity + translateY（スクロール出現）
  ブラー:        backdrop-filter: blur(20px)（ナビ半透明）
  ステージ照明:   黒背景 + プロダクト画像のみ光る演出
  グラデーション: linear-gradient（ダーク背景のフェード）

Animation principles:
  transition:    0.2s - 0.3s ease
  意味のある動きだけを使う。装飾的アニメーションは禁止
```

---

## Do's and Don'ts

### Do
- カラーパレット以外の色を使わない
- フォントは上記2種類（日本語 + 英語）のみ使う
- ボタンはComponent Stylingsの定義通りに作る
- 画像にはalt属性を必ず付ける
- 余白に迷ったら「多すぎるかも」と思う量が正解
- ダーク↔ライトのセクション交互配色で区切りを作る
- フルブリード背景 + 狭いコンテンツ幅（980px）で高級感を出す
- 8pxグリッドに基づいてスペーシングする

### Don't
- グラデーション背景を多用しない
- フォントを3種類以上使わない
- コントラスト比 4.5:1 を下回るテキストを置かない
- 意味なく大量のアニメーションを使わない
- 中途半端なコントラスト差をつけない（やるなら大胆に）
- Edge-to-edgeで文字を敷き詰めない（最低 22px の左右余白）
- ウェイトを4種類以上使わない（400 / 600 / 700 の3段階で十分）
- カード内にボーダーとシャドウを同時に使わない

---

*Based on Apple.com design system analysis — 2026-04-10*
