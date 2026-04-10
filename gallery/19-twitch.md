# DESIGN.md — Twitch風デザインシステム

> パープル×ダークのライブストリーミングプラットフォーム向けデザインシステム

---

## Project Overview

- **Project Name**: StreamHub — ライブ配信＆コミュニティプラットフォーム
- **Vibe**: "深い闇の中で鮮やかに輝くパープル。エネルギッシュで遊び心があり、ライブの熱量を画面越しに伝えるエンタメ空間"
- **Target User**: ゲーマー・配信者・10〜30代のエンタメ好きユーザー

---

## Color Palette & Roles

```
Primary:      #9146FF   （メインCTA・リンク・ブランドカラー）
Secondary:    #BF94FF   （サブアクション・タグ・ホバー状態）
Background:   #0E0E10   （ページ背景）
Surface:      #18181B   （カード・パネル背景）
Text:         #EFEFF1   （本文テキスト）
Text-muted:   #ADADB8   （補足テキスト・キャプション）
Accent:       #FF4747   （ライブバッジ・通知・警告）
Border:       #2F2F35   （区切り線・枠線）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA） — #EFEFF1 on #0E0E10 = 16.4:1 ✓
- Primary on Background: #9146FF on #0E0E10 = 5.0:1 ✓
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", sans-serif
Base size:     14px（情報密度が高いため小さめ）
Line height:   1.5
Letter spacing: 0.01em

Heading weights:
  H1: ExtraBold（800）、32px
  H2: Bold（700）、24px
  H3: Bold（700）、20px
  H4: SemiBold（600）、16px

Body: Regular（400）、14px
Small: Regular（400）、12px
Caption: Regular（400）、11px

見出しは太く、力強く。コンテンツは密度高く並べる。
```

---

## Component Stylings

### Button
```
Border radius:  4px
Padding:        8px 16px
Min width:      80px
Font weight:    SemiBold（600）
Font size:      13px

Primary button:
  background: #9146FF
  color: #FFFFFF
  hover: #772CE8

Secondary button:
  background: rgba(255, 255, 255, 0.08)
  border: none
  color: #EFEFF1
  hover background: rgba(255, 255, 255, 0.15)

Icon button:
  width: 36px
  height: 36px
  border-radius: 4px
  background: transparent
  hover background: rgba(255, 255, 255, 0.08)
```

### Card（配信カード）
```
Border radius:  6px
Padding:        0px（画像がカード全面を覆う）
Background:     #18181B
Border:         none
Shadow:         none
Hover:          transform translateY(-2px), border: 2px solid #9146FF

Thumbnail:
  Aspect ratio: 16:9
  Border radius: 6px 6px 0 0
  Overlay: ライブバッジ（左上に赤い #FF4747 バッジ）

Info area:
  Padding: 10px
  Streamer avatar: 40px, border-radius 50%
  Title: 14px, Bold, 2行まで
  Category: 12px, Text-muted
  Viewer count: 12px, Text-muted
```

### Input / Form
```
Border radius:  6px
Border:         none
Background:     #2F2F35
Padding:        8px 12px
Font size:      14px
Color:          #EFEFF1
Placeholder:    #7A7A85
Focus outline:  2px solid #9146FF
```

### Navigation
```
Height:         50px
Background:     #18181B
Logo width:     90px
Link spacing:   16px
Link font size: 13px
Link color:     #ADADB8
Link hover:     #EFEFF1
Active:         #9146FF
Border-bottom:  none（ナビとコンテンツの間にボーダーなし）
```

### Chat Panel
```
Width:          340px
Background:     #18181B
Border-left:    1px solid #2F2F35
Message padding: 4px 16px
Username color:  ランダムカラー（配信者が設定可能）
Message font:    13px
Input height:    40px
Send button:     #9146FF
```

---

## Layout Principles

```
Max width:        制限なし（フル幅レイアウト）
Outer padding:    0px（コンテンツは画面いっぱいに広げる）
Section spacing:  24px
Grid columns:     可変（カード幅300px基準のオートフィット）
Gutter:           10px
Sidebar:          左サイドバー 50px（アイコンのみ）、展開時 240px
```

---

## Do's and Don'ts

### Do
- コンテンツ（配信サムネイル）をとにかく多く表示する。情報密度を高く保つ
- パープル（#9146FF）はインタラクティブ要素とブランド要素のみに使う
- ライブ感を演出するために赤いバッジ（#FF4747）を効果的に使う
- ホバー時のフィードバックを明確にする（UI操作の手応えを重視）
- アバターやバッジで配信者のアイデンティティを表現する

### Don't
- 余白を取りすぎない（エンタメUIは密度が命）
- パープルを背景色として広範囲に使わない
- 明るい配色にしない（ダークモードがデフォルトかつ唯一のモード）
- テキストを長文で表示しない（短く、パッと読める情報設計にする）
- ボーダーを多用しない（暗い色の階層で分離する）
- 角丸を大きくしすぎない（最大6px程度に抑える）

---

*Template version: 1.0 — 2026-04-10*
