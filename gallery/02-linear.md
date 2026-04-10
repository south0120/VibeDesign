# DESIGN.md — Linear風 プロダクティビティツール ダークデザイン

---

## Project Overview

- **Project Name**: Linear風 — ダークモード プロダクティビティデザイン
- **Vibe**: "静かな集中力。暗闇の中で光るインターフェースが、チームの生産性を最大化する。無駄を削ぎ落としたプロのツール"
- **Target User**: ソフトウェア開発チーム・プロダクトマネージャー

---

## Color Palette & Roles

```
Primary:      #5E6AD2   （メインCTA・リンク・ブランドカラー — Linear Indigo）
Secondary:    #8B5CF6   （サブアクション・タグ・ステータスバッジ）
Background:   #000000   （ページ背景・純粋な黒）
Surface:      #1A1A2E   （カード・サイドバー・モーダル背景）
Text:         #EEEEEE   （本文テキスト・メインコンテンツ）
Text-muted:   #6B6F76   （補足テキスト・キャプション・プレースホルダー）
Accent:       #F59E0B   （警告・進行中ステータス）
Border:       #2A2A3C   （区切り線・枠線・ダークな境界）
```

**追加ステータスカラー:**
```
Success:      #22C55E   （完了・成功）
Warning:      #F59E0B   （注意・進行中）
Error:        #EF4444   （エラー・緊急）
Info:         #5E6AD2   （情報・Primary流用）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上 — #EEEEEE on #000000 = 18.1:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", -apple-system, BlinkMacSystemFont, sans-serif
Base size:     14px
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: SemiBold（600）、32px
  H2: SemiBold（600）、24px
  H3: Medium（500）、18px
  H4: Medium（500）、16px

Body: Regular（400）、14px
Small: Regular（400）、12px
Caption: Regular（400）、11px
```

**特記:** 情報密度が高いツールのため、Base sizeは14pxと小さめ。行間も1.6と締める。

---

## Component Stylings

### Button
```
Border radius:  6px
Padding:        8px 16px
Min width:      80px
Font weight:    Medium（500）
Font size:      13px
Transition:     all 0.1s ease

Primary button:
  background: #5E6AD2
  color: #FFFFFF
  hover: background #6E7AE2, brightness(1.1)

Secondary button:
  background: transparent
  border: 1px solid #2A2A3C
  color: #EEEEEE
  hover: background rgba(94, 106, 210, 0.1), border-color #5E6AD2

Ghost button:
  background: transparent
  color: #6B6F76
  hover: color #EEEEEE, background rgba(255, 255, 255, 0.05)
```

### Card
```
Border radius:  8px
Padding:        16px
Border:         1px solid #2A2A3C
Shadow:         none（フラットデザイン）
Background:     #1A1A2E
Hover:          border-color #5E6AD2（選択可能な場合）
```

### Input / Form
```
Border radius:  6px
Border:         1px solid #2A2A3C
Padding:        8px 12px
Font size:      14px
Background:     #0D0D1A
Color:          #EEEEEE
Focus outline:  2px solid #5E6AD2
Placeholder:    #6B6F76
```

### Navigation (Sidebar)
```
Width:          240px
Background:     #0D0D1A
Logo width:     100px
Item padding:   8px 12px
Item radius:    6px
Active item:    background rgba(94, 106, 210, 0.15), color #EEEEEE
Hover item:     background rgba(255, 255, 255, 0.05)
Section label:  11px, #6B6F76, uppercase, letter-spacing 0.05em
```

### Command Palette (⌘K)
```
Width:          640px
Max height:     400px
Background:     #1A1A2E
Border:         1px solid #2A2A3C
Border radius:  12px
Shadow:         0 16px 48px rgba(0, 0, 0, 0.6)
Backdrop:       rgba(0, 0, 0, 0.5) + backdrop-filter blur(4px)
Input padding:  16px 20px
Result padding: 10px 20px
```

---

## Layout Principles

```
Max width:        1400px（サイドバー込み）
Content width:    1000px（メインコンテンツ）
Sidebar width:    240px
Outer padding:    0px（アプリUIのためフル画面）
Section spacing:  32px
Grid columns:     自由配置（リスト・カンバン等の用途に応じて）
Gutter:           16px
```

**特徴的なレイアウトルール:**
- サイドバー＋メインコンテンツの2カラムレイアウトが基本
- テーブル・リストビューでは行の高さは40px〜48pxで統一
- コンパクトな情報表示を優先し、余白は最小限

---

## Do's and Don'ts

### Do
- キーボードショートカットをすべてのアクションに用意する
- アニメーションは0.1s以下の瞬時フィードバックにする
- ステータスカラーは上記の定義に従う
- コマンドパレット（⌘K）を中心操作として設計する
- アイコンは16×16px、ストローク幅1.5pxで統一する
- Surface色を使ってレイヤーの階層を表現する

### Don't
- 白背景のセクションを挿入しない（ダークモード一貫性を保つ）
- ボタンに影（box-shadow）を付けない — フラットが原則
- テキストを16px以上に大きくしない（H1見出しを除く）
- hover以外の場面で色を変化させない
- グラデーションを使わない（Primary色のソリッドカラーのみ）
- 角丸を12px以上にしない（コマンドパレットを除く）

---

*Generated: 2026-04-10 — Linear inspired design system*
