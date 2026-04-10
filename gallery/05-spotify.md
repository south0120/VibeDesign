# DESIGN.md — Spotify風 ダーク×グリーン エンターテインメント

---

## Project Overview

- **Project Name**: Spotify風 — ダーク×グリーン エンターテインメント
- **Vibe**: "音楽に没入するためのダークUI。グリーンのアクセントがエネルギーとアクションを象徴する"
- **Target User**: 音楽・エンタメサービスのユーザー、若年層クリエイター

---

## Color Palette & Roles

```
Primary:      #1DB954   （メインCTA・再生ボタン・ブランドカラー）
Secondary:    #1ED760   （ホバー状態・アクティブ要素）
Background:   #121212   （ページ背景・ダークベース）
Surface:      #181818   （カード・セクション背景）
Text:         #FFFFFF   （本文テキスト）
Text-muted:   #B3B3B3   （補足テキスト・歌詞・タイムスタンプ）
Accent:       #FF6437   （ポッドキャスト・新着バッジ）
Border:       #282828   （区切り線・枠線）
```

**コントラスト比**: #FFFFFF on #121212 = 15.9:1 ✓

---

## Typography Rules

```
Font:          "Circular", "Noto Sans JP", sans-serif
Font-en:       "Circular", "Helvetica Neue", Arial, sans-serif
Base size:     16px
Line height:   1.5
Letter spacing: 0.015em

Heading weights:
  H1: Bold（700）、56px
  H2: Bold（700）、36px
  H3: Bold（700）、24px
  H4: SemiBold（600）、18px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

---

## Component Stylings

### Button
```
Border radius:  500px
Padding:        14px 32px
Font weight:    Bold（700）
Font size:      16px

Primary: background #1DB954, color #000000
Secondary: transparent, border 1px solid #FFFFFF, color #FFFFFF
```

### Card
```
Border radius:  8px
Padding:        16px
Background:     #181818
Hover:          background #282828
```

### Navigation
```
Height:         64px
Background:     #000000
Sidebar width:  280px
```

---

## Layout Principles

```
Max width:        1440px
Outer padding:    32px（モバイルは 16px）
Section spacing:  48px
Grid columns:     12
Gutter:           24px
```

---

## Do's and Don'ts

### Do
- ダーク背景を基本とする（#121212）
- グリーンはアクション要素にのみ使用
- カード背景はホバーで明るくする

### Don't
- グリーンをテキストカラーに使わない
- 完全な黒（#000000）を背景にしない（#121212を使う）
- カードにボーダーやシャドウを追加しない

---

*Inspired by Spotify — 2026-04-10*
