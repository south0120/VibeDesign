# DESIGN.md — Vercel風 デベロッパー モノクロデザイン

---

## Project Overview

- **Project Name**: Vercel風 — モノクロ×アクセント デベロッパーデザイン
- **Vibe**: "漆黒のキャンバスに白い文字が浮かぶ。速度と精密さを体現する、開発者のための究極のモノクロ美学"
- **Target User**: フロントエンド開発者・DevOpsエンジニア・テック企業

---

## Color Palette & Roles

```
Primary:      #000000   （メインCTA・ブランドカラー — 純黒ボタン）
Secondary:    #666666   （サブアクション・セカンダリボタン）
Background:   #000000   （ページ背景・純黒）
Surface:      #111111   （カード・セクション背景・わずかに明るい黒）
Text:         #EDEDED   （本文テキスト・メインコンテンツ）
Text-muted:   #888888   （補足テキスト・キャプション）
Accent:       #0070F3   （リンク・インタラクティブ要素・ブルーアクセント）
Border:       #333333   （区切り線・枠線）
```

**追加カラー:**
```
Success:      #50E3C2   （デプロイ成功・ターコイズグリーン）
Error:        #E00      （エラー・ビルド失敗）
Warning:      #F5A623   （警告）
Gradient-1:   #FF0080   （グラデーション用ピンク）
Gradient-2:   #7928CA   （グラデーション用パープル）
Gradient-3:   #FF4D4D   （グラデーション用レッド）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上 — #EDEDED on #000000 = 17.4:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", -apple-system, BlinkMacSystemFont, sans-serif
Base size:     16px
Line height:   1.6
Letter spacing: -0.02em（英語見出しはタイトに）

Heading weights:
  H1: Bold（700）、64px（ヒーロー見出し・インパクト重視）
  H2: Bold（700）、48px
  H3: SemiBold（600）、28px
  H4: SemiBold（600）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px, #888888
Mono: "Geist Mono", "SF Mono", monospace, 14px
```

**特記:** 見出しは大きく・太く。letter-spacingを負の値にしてタイトな印象を作る。

---

## Component Stylings

### Button
```
Border radius:  8px（角丸はやや控えめ）
Padding:        10px 24px
Min width:      auto
Font weight:    Medium（500）
Font size:      14px
Transition:     all 0.15s ease
Height:         40px

Primary button:
  background: #EDEDED
  color: #000000
  hover: background #FFFFFF
  ※ダーク背景なので白ボタンが Primary

Secondary button:
  background: transparent
  border: 1px solid #333333
  color: #EDEDED
  hover: border-color #888888, background rgba(255, 255, 255, 0.05)

Blue link button:
  background: transparent
  color: #0070F3
  hover: color #3291FF
  text-decoration: underline on hover
```

### Card
```
Border radius:  12px
Padding:        24px
Border:         1px solid #333333
Shadow:         none
Background:     #111111
Hover:          border-color #888888
Transition:     border-color 0.15s ease
```

### Input / Form
```
Border radius:  8px
Border:         1px solid #333333
Padding:        10px 14px
Font size:      14px
Background:     #000000
Color:          #EDEDED
Height:         40px
Focus outline:  none
Focus border:   1px solid #888888
Placeholder:    #666666
```

### Navigation
```
Height:         64px
Background:     rgba(0, 0, 0, 0.5)
Backdrop-filter: saturate(180%) blur(20px)
Border-bottom:  1px solid #333333
Logo width:     80px（▲三角ロゴ）
Link spacing:   24px
Link font-size: 14px
Link color:     #888888
Link hover:     #EDEDED
Active link:    #EDEDED
```

### Badge / Tag
```
Border radius:  9999px（完全な丸）
Padding:        4px 10px
Font size:      12px
Font weight:    Medium（500）
Background:     rgba(255, 255, 255, 0.1)
Color:          #EDEDED
Border:         1px solid #333333
```

### Terminal / Code Block
```
Background:     #111111
Border:         1px solid #333333
Border radius:  8px
Padding:        20px
Font:           "Geist Mono", monospace
Font size:      14px
Line height:    1.6
Color:          #EDEDED
Prompt symbol:  #888888 "▲" or "$"
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    48px（モバイル: 24px）
Section spacing:  160px（セクション間は大胆に空ける）
Grid columns:     12
Gutter:           24px
Hero height:      100vh（ファーストビューはフルスクリーン）
```

**特徴的なレイアウトルール:**
- ヒーローは100vhフルスクリーン、中央にH1を大きく配置
- セクション間は160pxと極めて広く、ドラマチックな間を演出
- テキストグラデーション（linear-gradient）を見出しに適用して視覚的アクセントを加える
- グリッドの境界線を可視化するような「構造を見せる」デザイン

---

## Do's and Don'ts

### Do
- 見出しにテキストグラデーション（#FF0080→#7928CA→#FF4D4D）を適用する
- ナビゲーションにはglassmorphism（背景ブラー）を使う
- デプロイステータスには #50E3C2（成功）と #E00（失敗）を使う
- コードブロックとターミナル表示を多用する
- ボーダーカラー（#333333）を使ってグリッド感を出す
- 数値やメトリクスはモノスペースフォントで表示する

### Don't
- 白背景のセクションを作らない（全面ダーク統一）
- テキストに影を付けない
- #333333 より明るいボーダーを使わない（#888888はhoverのみ）
- 角丸を16px以上にしない（バッジの pill 形状を除く）
- カラフルな塗りのアイコンを使わない（線画アイコンのみ）
- Surface背景の上にさらにSurface背景のカードを入れ子にしない

---

*Generated: 2026-04-10 — Vercel inspired design system*
