# DESIGN.md — リキッドグラス風（iOS風）

> iPhone / iOS のデザイン言語にインスパイアされた半透明ガラスエフェクト。  
> 背景ぼかしと大きめの角丸で、軽やかさと洗練を両立する。

---

## Project Overview

- **Project Name**: リキッドグラス風デザイン
- **Vibe**: "iOSのような透明感と軽やかさ。ガラス越しに世界を見るような洗練されたUI体験"
- **Target User**: モダンなSaaSプロダクト利用者、Apple製品に親しみのあるユーザー

---

## Color Palette & Roles

```
Primary:      #007AFF   （メインCTA・リンク・ブランドカラー。iOS Blue）
Secondary:    #5856D6   （サブアクション・タグ。インディゴ）
Background:   #F2F2F7   （ページ背景。iOSシステムグレー6）
Surface:      rgba(255,255,255,0.72)（カード・セクション背景。半透明白）
Text:         #1C1C1E   （本文テキスト。iOSラベルカラー）
Text-muted:   #8E8E93   （補足テキスト。iOSセカンダリラベル）
Accent:       #FF9500   （強調・警告・バッジ。iOSオレンジ）
Border:       rgba(0,0,0,0.08)（区切り線・枠線。極薄ボーダー）
```

**コントラスト比の必須要件**
- Body text（#1C1C1E on #F2F2F7）: 約 15.3:1（WCAG AAA適合）
- Text-muted（#8E8E93 on #F2F2F7）: 約 3.5:1（Large textのみWCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

**ダークモード対応値**
```
Background:   #000000
Surface:      rgba(44,44,46,0.72)
Text:         #FFFFFF
Text-muted:   #8E8E93
Border:       rgba(255,255,255,0.08)
```

---

## Typography Rules

```
Font:          "SF Pro", -apple-system, BlinkMacSystemFont, sans-serif
Font-ja:       "Hiragino Sans", "Hiragino Kaku Gothic ProN", sans-serif
Base size:     17px（iOSのBodyサイズに準拠）
Line height:   1.47（iOS準拠の22px / 15px相当）
Letter spacing: -0.01em（SF Proのデフォルトトラッキング）

Heading weights:
  H1: Bold（700）、34px
  H2: Bold（700）、28px
  H3: SemiBold（600）、22px
  H4: SemiBold（600）、20px

Body: Regular（400）、17px
Small: Regular（400）、15px
Caption: Regular（400）、13px
```

**スタイルノート**
- SF Pro が利用できない環境では -apple-system → system-ui にフォールバック
- 日本語テキストには Hiragino Sans を優先使用
- フォントウェイトは Regular / SemiBold / Bold の3段階のみ

---

## Component Stylings

### Button
```
Border radius:  20px（カプセル型。iOS風の大きめ角丸）
Padding:        14px 28px
Min width:      120px
Font weight:    SemiBold（600）
Font size:      17px

Primary button:
  background: #007AFF
  color: #FFFFFF
  border: none
  hover → background: #0056CC
  active → transform: scale(0.97)
  transition: all 0.2s ease

Secondary button:
  background: rgba(0,122,255,0.12)
  border: none
  color: #007AFF
  hover → background: rgba(0,122,255,0.2)

Text button:
  background: transparent
  border: none
  color: #007AFF
  hover → opacity: 0.7
```

### Card
```
Border radius:  16px
Padding:        20px
Border:         none（ボーダーではなく背景の透過で区切る）
Background:     rgba(255,255,255,0.72)
Backdrop-filter: blur(40px) saturate(180%)
-webkit-backdrop-filter: blur(40px) saturate(180%)
Shadow:         0 2px 12px rgba(0,0,0,0.06)

ホバー時:
  shadow: 0 4px 20px rgba(0,0,0,0.1)
  transition: box-shadow 0.3s ease
```

### Input / Form
```
Border radius:  12px
Border:         none
Padding:        12px 16px
Font size:      17px
Background:     rgba(118,118,128,0.12)（iOSのテキストフィールド背景）
Focus:
  outline: none
  box-shadow: 0 0 0 4px rgba(0,122,255,0.3)
Placeholder:    color #8E8E93
```

### Navigation
```
Height:         56px
Background:     rgba(255,255,255,0.72)
Backdrop-filter: blur(40px) saturate(180%)
-webkit-backdrop-filter: blur(40px) saturate(180%)
Border-bottom:  0.5px solid rgba(0,0,0,0.08)
Logo width:     110px
Link spacing:   28px
Link style:     color: #007AFF, font-weight: 600
Active:         font-weight: 700
Position:       sticky, top: 0, z-index: 100
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    64px（モバイルは 20px）
Section spacing:  80px
Grid columns:     12
Gutter:           24px

特記事項:
- カードやモーダルには必ず backdrop-filter を適用
- z-indexの階層を意識し、ガラス要素が重なる場合は背景の透過率を調整
- iOS準拠のセーフエリアを考慮（env(safe-area-inset-*)）
- 背景にはグラデーションメッシュや写真を配置し、ガラス効果を活かす
- アニメーションは spring 系の easing（cubic-bezier(0.25, 0.46, 0.45, 0.94)）を使用
```

---

## Do's and Don'ts

### Do
- すべてのカード・パネルに backdrop-filter: blur(40px) saturate(180%) を適用する
- 角丸は 12px 以上を基本とし、iOS的な柔らかさを保つ
- SF Pro / -apple-system フォントを一貫して使用する
- 半透明の背景色（rgba）でレイヤー感を出す
- ボーダーは 0.5px〜1px の極細ラインで控えめに使う

### Don't
- 不透明なベタ塗り背景でカードを作らない（透明感を損なう）
- 角丸を 8px 未満にしない
- ハードなドロップシャドウを使わない（blur値は必ず 8px 以上）
- backdrop-filter 非対応ブラウザのフォールバックを忘れない
- ボーダーを 2px 以上の太さにしない
- フォントを 3 種類以上使わない

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*

---

## CSS / Component Examples

```css
/* リキッドグラス カード */
.glass-card {
  background: rgba(255, 255, 255, 0.72);
  backdrop-filter: blur(40px) saturate(180%);
  -webkit-backdrop-filter: blur(40px) saturate(180%);
  border-radius: 20px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.08);
  padding: 24px;
}

/* フロスト効果ナビバー */
.glass-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  height: 56px;
  background: rgba(242, 242, 247, 0.6);
  backdrop-filter: blur(40px) saturate(180%);
  border-bottom: 0.5px solid rgba(0, 0, 0, 0.08);
}
```
