# DESIGN.md — Arc Browser風デザインシステム

> グラデーション×カラフルなブラウザUI。遊び心のあるダークインターフェース。

---

## Project Overview

- **Project Name**: ARC Chromatic — カラフルグラデーションUIシステム
- **Vibe**: "ダークな背景にグラデーションが呼吸するように浮かぶ。機能的でありながら、色彩の楽しさを忘れない次世代インターフェース"
- **Target User**: 20〜35代のテック感度の高いクリエイター、開発者、パワーユーザー

---

## Color Palette & Roles

```
Primary:      #6C5CE7   （メインCTA・リンク。鮮やかなパープル）
Secondary:    #00CEC9   （サブアクション・タグ。ティールグリーン）
Background:   #1A1625   （ページ背景。深いダークパープル）
Surface:      #2D2640   （カード・セクション背景。少し明るいダークパープル）
Text:         #FFFFFF   （本文テキスト。白）
Text-muted:   #9B8FC2   （補足テキスト。ラベンダーグレー）
Accent:       #FD79A8   （強調・通知・バッジ。コーラルピンク）
Border:       #3D3555   （区切り線・枠線。パープル寄りのグレー）
```

**グラデーション定義**
```
Gradient-primary:   linear-gradient(135deg, #6C5CE7 0%, #A29BFE 100%)
Gradient-accent:    linear-gradient(135deg, #FD79A8 0%, #FDCB6E 100%)
Gradient-cool:      linear-gradient(135deg, #00CEC9 0%, #6C5CE7 100%)
Gradient-warm:      linear-gradient(135deg, #E17055 0%, #FD79A8 100%)
Gradient-bg-glow:   radial-gradient(ellipse at 30% 20%, rgba(108,92,231,0.15) 0%, transparent 60%)
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #FFFFFF on #1A1625 = 15.8:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", sans-serif
Base size:     14px（UIツール向けにやや小さめ）
Line height:   1.6
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、32px
  H2: SemiBold（600）、24px
  H3: SemiBold（600）、18px
  H4: Medium（500）、16px

Body: Regular（400）、14px
Small: Regular（400）、12px
Caption: Medium（500）、11px、letter-spacing: 0.04em
```

---

## Component Stylings

### Button
```
Border radius:  12px
Padding:        10px 20px
Min width:      100px
Font weight:    SemiBold（600）
Font size:      14px

Primary button:
  background: Gradient-primary（linear-gradient(135deg, #6C5CE7, #A29BFE)）
  color: #FFFFFF
  border: none
  box-shadow: 0 4px 16px rgba(108,92,231,0.4)
  hover: box-shadow 0 6px 24px rgba(108,92,231,0.6), transform translateY(-1px)
  transition: all 0.2s ease

Secondary button:
  background: rgba(108,92,231,0.15)
  border: 1px solid rgba(108,92,231,0.3)
  color: #A29BFE
  hover: background rgba(108,92,231,0.25)

Ghost button:
  background: transparent
  border: none
  color: #9B8FC2
  hover: color #FFFFFF
```

### Card
```
Border radius:  16px
Padding:        20px
Border:         1px solid #3D3555
Shadow:         0 4px 24px rgba(0,0,0,0.3)
Background:     #2D2640
Backdrop-filter: blur(8px)（半透明カードの場合は background: rgba(45,38,64,0.8)）
Hover:          border-color #6C5CE7, box-shadow 0 8px 32px rgba(108,92,231,0.2)
```

### Input / Form
```
Border radius:  10px
Border:         1px solid #3D3555
Padding:        10px 16px
Font size:      14px
Background:     rgba(45,38,64,0.6)
Color:          #FFFFFF
Placeholder:    #9B8FC2
Focus outline:  border-color #6C5CE7, box-shadow 0 0 0 3px rgba(108,92,231,0.2)
```

### Navigation / Sidebar
```
Width:          260px（サイドバー型ナビゲーション）
Background:     #1A1625
Padding:        16px
Item height:    36px
Item radius:    8px
Item hover:     background rgba(108,92,231,0.12)
Item active:    background rgba(108,92,231,0.2), color #FFFFFF
Divider:        1px solid #3D3555
```

### Tab Bar
```
Height:         40px
Background:     rgba(45,38,64,0.6)
Border radius:  10px
Tab padding:    8px 16px
Active tab:
  background: Gradient-primary
  border-radius: 8px
  color: #FFFFFF
  box-shadow: 0 2px 8px rgba(108,92,231,0.3)
```

### Tooltip / Popover
```
Border radius:  12px
Padding:        12px 16px
Background:     #2D2640
Border:         1px solid #3D3555
Shadow:         0 8px 32px rgba(0,0,0,0.4)
Font size:      13px
Color:          #FFFFFF
```

---

## Layout Principles

```
Max width:        1200px
Outer padding:    40px（モバイルは 16px）
Section spacing:  80px
Grid columns:     12
Gutter:           20px
```

**レイアウトの特徴**
- サイドバー + メインコンテンツの 2 カラム構成を基本とする
- 背景にグラデーションのグロー（光の粒）を配置して奥行きを出す
- カードは半透明 + backdrop-filter で立体感を演出
- コンパクトな UI 要素で情報密度を高める

---

## Do's and Don'ts

### Do
- グラデーションを CTA ボタンやアクティブ状態のハイライトに使い、視線を誘導する
- 背景にグラデーションの微かなグロー効果を入れて空間に奥行きを出す
- カードやポップオーバーには backdrop-filter: blur() を活用する
- カラーパレットの色を組み合わせたグラデーションで楽しさを表現する
- ダークテーマの中で、色のコントラストを使って重要な要素を目立たせる

### Don't
- グラデーションを全面に敷き詰めない。ポイント使いで効果を最大化する
- 背景 (#1A1625) と Surface (#2D2640) 以外のダークカラーを追加しない
- テキストにグラデーションを多用しない（見出し 1 箇所程度に留める）
- ボーダーを太くしない。1px + 低い不透明度でさりげなく
- ライトモードに安易に切り替えない。ダークを前提に設計する
- グロー効果（box-shadow）を全要素に付けない。CTAと重要カードだけに絞る

---

*Template version: 1.0 — 2026-04-10 Procebo webinar*
