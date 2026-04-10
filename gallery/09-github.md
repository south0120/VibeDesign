# DESIGN.md — GitHub風デベロッパープラットフォーム

> 開発者が最も快適に過ごせる、ダークテーマ基調のデベロッパープラットフォームのデザインシステム。

---

## Project Overview

- **Project Name**: DevForge — デベロッパーのためのコード共有・コラボレーションプラットフォーム
- **Vibe**: "開発者のホームグラウンド。ダークUIでコードが映え、情報密度が高くても読みやすい。機能的で誠実、無駄のないインターフェース"
- **Target User**: 20〜50歳のソフトウェアエンジニア、オープンソースコントリビューター

---

## Color Palette & Roles

```
Primary:      #238636   （メインCTA・マージボタン・成功状態）
Secondary:    #1F6FEB   （リンク・PR番号・ブランチ名）
Background:   #0D1117   （ページ背景。深いダークブルー）
Surface:      #161B22   （カード・セクション・サイドバー背景）
Text:         #E6EDF3   （本文テキスト。柔らかい白）
Text-muted:   #8B949E   （補足テキスト・タイムスタンプ）
Accent:       #F85149   （エラー・クローズ・破壊的アクション）
Border:       #30363D   （区切り線・枠線）

Extended colors:
  Warning:    #D29922   （警告・注意バッジ）
  Purple:     #8957E5   （レビュー依頼・ドラフト）
  Coral:      #F78166   （コントリビューショングラフ）
```

**コントラスト比の必須要件**
- Body text（#E6EDF3 on #0D1117）: 13.3:1 ✅ WCAG AAA
- Text-muted（#8B949E on #0D1117）: 4.6:1 ✅ WCAG AA
- Primary（#238636 on #0D1117）: 3.8:1 ✅ Large text AA
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "-apple-system", "Segoe UI", "Helvetica Neue", sans-serif
Font-mono:     "JetBrains Mono", "SFMono-Regular", monospace
Base size:     14px
Line height:   1.5
Letter spacing: 0em

Heading weights:
  H1: Bold（600）、32px
  H2: Bold（600）、24px
  H3: SemiBold（600）、20px
  H4: SemiBold（600）、16px

Body: Regular（400）、14px
Small: Regular（400）、12px
Caption: Regular（400）、12px
Code: Regular（400）、13px（Font-mono使用）
```

---

## Component Stylings

### Button
```
Border radius:  6px
Padding:        5px 16px
Min width:      auto
Font weight:    SemiBold（600）
Font size:      14px
Line height:    20px

Primary button（Green）:
  background: #238636
  color: #FFFFFF
  border: 1px solid rgba(240,246,252,0.1)

Secondary button:
  background: #21262D
  border: 1px solid #30363D
  color: #C9D1D9
  border-radius: 6px

Danger button:
  background: transparent
  border: 1px solid #F85149
  color: #F85149
  Hover: background #DA3633, color #FFFFFF

Hover state:
  Primary: background #2EA043
  Secondary: background #30363D, border-color #8B949E
```

### Card / Box
```
Border radius:  6px
Padding:        16px
Border:         1px solid #30363D
Shadow:         none
Background:     #0D1117 または #161B22
```

### Input / Form
```
Border radius:  6px
Border:         1px solid #30363D
Padding:        5px 12px
Font size:      14px
Focus outline:  2px solid #1F6FEB（blue glow）
Background:     #0D1117
Color:          #E6EDF3
```

### Navigation
```
Height:         62px
Background:     #161B22
Border-bottom:  1px solid #30363D
Logo width:     32px（Octocat）
Logo color:     #E6EDF3
Link spacing:   16px
Link color:     #E6EDF3（opacity 0.7 → hover 1.0）
Search bar:     border-radius 6px, background #0D1117, border 1px solid #30363D, width 272px
```

---

## Layout Principles

```
Max width:        1280px
Outer padding:    32px（デスクトップ）/ 16px（モバイル）
Section spacing:  32px
Grid columns:     12
Gutter:           24px
Sidebar width:    296px（リポジトリページ）
Main content:     flex-grow（残り幅）
Breakpoints:      768px（タブレット）/ 1012px（デスクトップ）/ 1280px（ワイド）
```

---

## Do's and Don'ts

### Do
- コードブロックには必ずシンタックスハイライトを適用する
- モノスペースフォントをコード・パス・コマンドに一貫して使う
- ボーダー（#30363D）でセクションを区切り、視覚的な階層を作る
- ラベル・バッジでステータス（Open/Closed/Merged）を色分けする
- 情報密度を高く保ちつつ、セクション間のスペースで呼吸させる
- アイコンは16px Octicons スタイルで統一する

### Don't
- ライトモードの色（#FFFFFF背景）をダークUI内に混在させない
- 角丸を12px以上にしない（開発ツールとしてのシャープさを維持）
- Primary green（#238636）を装飾目的で使わない（アクション専用）
- テキストリンクに下線以外の装飾（背景色ハイライト等）を付けない
- 画像やイラストを多用しない（テキストとデータが主役）
- グラデーションやグロー効果を使わない（フラットでソリッドなスタイル）

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
