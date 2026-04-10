# DESIGN.md — 37: ターミナル・ハッカー

> モノスペースフォント、グリーン・オン・ブラック。  
> レトロなCRTターミナルの雰囲気を再現し、ハッカー映画のような没入感を演出。

---

## Project Overview

- **Project Name**: Terminal Hacker UI
- **Vibe**: "映画に出てくるハッカーの端末。グリーンの文字が黒い画面に浮かび上がり、scanlineが走る"
- **Target User**: 開発者、エンジニア、サイバーセキュリティ関連、テック系コミュニティ

---

## Color Palette & Roles

```
Primary:      #00FF00   （メインCTA・リンク・ブランドカラー。マトリックスグリーン）
Secondary:    #00CC00   （サブアクション・ホバー状態。ダークグリーン）
Background:   #0C0C0C   （ページ背景。ほぼ純黒）
Surface:      #1A1A1A   （カード・セクション背景。ダークグレー）
Text:         #00FF00   （本文テキスト。グリーン）
Text-muted:   #00AA00   （補足テキスト・キャプション。ダルグリーン）
Accent:       #FFD700   （強調・警告・バッジ。ゴールド/イエロー — 警告・重要表示に使用）
Border:       #333333   （区切り線・枠線。ダークグレー）
```

**エラー・ステータス用**
```
Error:        #FF3333   （エラー表示。レッド）
Warning:      #FFD700   （警告表示。Accent と共通）
Success:      #00FF00   （成功表示。Primary と共通）
Info:         #00BFFF   （情報表示。シアンブルー）
```

**コントラスト比の必須要件**
- Text（#00FF00 on #0C0C0C）: 約9.5:1 ✓（WCAG AAA）
- Text-muted（#00AA00 on #0C0C0C）: 約5.8:1 ✓（WCAG AA）
- Accent（#FFD700 on #0C0C0C）: 約12.1:1 ✓（WCAG AAA）

---

## Typography Rules

```
Font:          "JetBrains Mono", "Fira Code", "Consolas", monospace
Font-en:       同上（すべてモノスペース）
Base size:     15px
Line height:   1.6
Letter spacing: 0.05em

Heading weights:
  H1: Bold（700）、28px — プレフィックス "# " を表示
  H2: Bold（700）、22px — プレフィックス "## " を表示
  H3: SemiBold（600）、18px — プレフィックス "### " を表示
  H4: Regular（400）、16px — プレフィックス "> " を表示

Body: Regular（400）、15px
Small: Regular（400）、13px
Caption: Regular（400）、11px
```

**特殊ルール**
- 全テキストはモノスペースフォントを使用。例外なし
- 見出しにはMarkdown風のプレフィックス（#, ##）を視覚的に表示
- テキストに微弱な `text-shadow: 0 0 8px rgba(0,255,0,0.5)` でグロー効果
- カーソル点滅アニメーション（blinkingcursor）を適宜使用

---

## Component Stylings

### Button
```
Border radius:  0px（角ばったターミナル風）
Padding:        10px 20px
Min width:      120px
Font weight:    Regular（400）
Font size:      15px
Font family:    "JetBrains Mono", monospace
Text transform: none（大文字にしない）

Primary button:
  background: #00FF00
  color: #0C0C0C
  border: 2px solid #00FF00
  text: "[ EXECUTE ]" 形式（角括弧で囲む）
  hover: background: #0C0C0C / color: #00FF00（反転）

Secondary button:
  background: transparent
  border: 1px solid #00FF00
  color: #00FF00
  text: "[ CANCEL ]" 形式
  hover: background: rgba(0,255,0,0.1)

Danger button:
  background: transparent
  border: 1px solid #FF3333
  color: #FF3333
  text: "[ DELETE ]" 形式
```

### Card
```
Border radius:  0px
Padding:        20px
Border:         1px solid #333333
Background:     #1A1A1A
Shadow:         none（フラット）
Header:         "┌─── タイトル ───┐" のようなASCIIボーダー風
Footer:         "└──────────────┘" のASCIIボーダー風
```

### Input / Form
```
Border radius:  0px
Border:         1px solid #333333
Background:     #0C0C0C
Padding:        10px 14px
Font size:      15px
Font family:    "JetBrains Mono", monospace
Color:          #00FF00
Placeholder:    #00AA00
Prefix:         "$ "（プロンプト記号を入力欄の先頭に表示）
Focus border:   1px solid #00FF00
Focus glow:     0 0 8px rgba(0,255,0,0.3)
Caret color:    #00FF00
```

### Navigation
```
Height:         48px
Background:     #0C0C0C
Border-bottom:  1px solid #333333
Logo:           ASCIIアート風テキストロゴ
Link spacing:   24px
Link color:     #00AA00
Link hover:     #00FF00
Active link:    #00FF00, prefix "> " を付ける
Link format:    "[home]  [about]  [contact]" のように角括弧で囲む
```

---

## Layout Principles

```
Max width:        960px（ターミナルは狭めの幅が雰囲気に合う）
Outer padding:    48px（モバイルは 16px）
Section spacing:  64px
Grid columns:     1（シングルカラム基本。必要時に2カラムまで）
Gutter:           24px
```

**Scanline効果**
```
- ページ全体にCSSオーバーレイでscanline（横線）を表示
- 実装: body::after に repeating-linear-gradient
  background: repeating-linear-gradient(
    0deg,
    rgba(0,0,0,0.15) 0px,
    rgba(0,0,0,0.15) 1px,
    transparent 1px,
    transparent 3px
  )
- pointer-events: none で操作を妨げない
- opacity: 0.3〜0.5 で控えめに
```

**CRTフリッカー効果（オプション）**
```
- 画面全体に微弱なフリッカーアニメーション
- @keyframes flicker { 0% { opacity: 0.97 } 50% { opacity: 1 } }
- animation: flicker 0.15s infinite
```

---

## Do's and Don'ts

### Do
- 全テキストにモノスペースフォントを使う（例外なし）
- ボタンやリンクは角括弧 `[ ]` で囲んでターミナルコマンド風にする
- 入力欄にはプロンプト記号 `$ ` を表示する
- テキストにグリーンのグロー（text-shadow）を適用して発光感を出す
- ロード時にタイピングアニメーション（1文字ずつ表示）を活用する

### Don't
- 角丸（border-radius）を使わない。ターミナルは全て直角
- グラデーション背景を使わない。背景はフラットな黒のみ
- 画像を多用しない。ASCIIアートやテキストベースの表現を優先
- フォントをサンセリフやセリフに変更しない
- scanline効果のopacityを0.6以上にしない（可読性が著しく下がる）

---

*Design: 37-terminal — Terminal Hacker UI*
