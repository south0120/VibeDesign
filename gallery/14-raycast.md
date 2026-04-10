# DESIGN.md — Raycast風 macOSネイティブ・ユーティリティ

---

## Project Overview

- **Project Name**: Raycast風 — macOSネイティブ・ユーティリティ
- **Vibe**: "macOSに溶け込む洗練されたダークUI。速さと効率を感じるプロツールのデザイン"
- **Target User**: macOSユーザー、開発者、パワーユーザー

---

## Color Palette & Roles

```
Primary:      #FF6363   （メインCTA・ブランドカラー）
Secondary:    #FBBF24   （セカンダリアクション・ハイライト）
Background:   #171717   （ページ背景）
Surface:      #222222   （カード・入力フィールド背景）
Text:         #EEEEEE   （本文テキスト）
Text-muted:   #888888   （補足テキスト・ショートカットキー）
Accent:       #6366F1   （リンク・選択状態）
Border:       #333333   （区切り線・枠線）
```

**コントラスト比**: #EEEEEE on #171717 = 14.4:1 ✓

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Font-en:       "Inter", system-ui, sans-serif
Base size:     15px
Line height:   1.5
Letter spacing: -0.01em

Heading weights:
  H1: Bold（700）、48px
  H2: SemiBold（600）、32px
  H3: SemiBold（600）、20px
  H4: Medium（500）、16px

Body: Regular（400）、15px
Mono: "JetBrains Mono", monospace
```

---

## Component Stylings

### Button
```
Border radius:  8px
Padding:        10px 20px
Font weight:    Medium（500）

Primary: background #FF6363, color #FFFFFF
Secondary: background #2A2A2A, border 1px solid #333333, color #EEEEEE
```

### Card
```
Border radius:  12px
Padding:        20px
Background:     #222222
Border:         1px solid #333333
Hover:          border-color #FF6363
```

### Navigation
```
Height:         56px
Background:     rgba(23, 23, 23, 0.8)
Backdrop:       blur(20px)
```

---

## Layout Principles

```
Max width:        1100px
Outer padding:    40px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px
```

---

## Do's and Don'ts

### Do
- macOSのビジュアル言語を参考にする
- キーボードショートカットを視覚的に表示
- ダークテーマを基本とする

### Don't
- 角丸を16px以上にしない
- 過度なアニメーションを使わない
- ライトモードをプライマリにしない

---

*Inspired by Raycast — 2026-04-10*
