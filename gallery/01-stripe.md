# DESIGN.md — Stripe風 FinTech クリーンデザイン

---

## Project Overview

- **Project Name**: Stripe風 — FinTech クリーンデザイン
- **Vibe**: "洗練された信頼感。決済インフラのように堅牢でありながら、開発者にとって心地よいクリーンさを持つプロフェッショナルデザイン"
- **Target User**: SaaSプロダクトを構築する開発者・スタートアップ創業者

---

## Color Palette & Roles

```
Primary:      #635BFF   （メインCTA・リンク・ブランドカラー — Stripe Purple）
Secondary:    #0A2540   （サブアクション・ダーク系ボタン・フッター背景）
Background:   #FFFFFF   （ページ背景・白ベース）
Surface:      #F6F9FC   （カード・セクション背景・薄いブルーグレー）
Text:         #0A2540   （本文テキスト・深いネイビー）
Text-muted:   #425466   （補足テキスト・キャプション）
Accent:       #00D4AA   （成功・完了・ポジティブインジケーター）
Border:       #E3E8EE   （区切り線・枠線・薄いグレー）
```

**コントラスト比の必須要件**
- Body text（Background上）: 4.5:1 以上（WCAG AA）— #0A2540 on #FFFFFF = 15.4:1 ✓
- Large text・見出し（Background上）: 3:1 以上（WCAG AA）
- 確認ツール: https://webaim.org/resources/contrastchecker/

---

## Typography Rules

```
Font:          "Noto Sans JP", sans-serif
Font-en:       "Inter", -apple-system, BlinkMacSystemFont, sans-serif
Base size:     16px
Line height:   1.7
Letter spacing: 0.01em

Heading weights:
  H1: Bold（700）、48px
  H2: Bold（700）、36px
  H3: SemiBold（600）、24px
  H4: SemiBold（600）、20px

Body: Regular（400）、16px
Small: Regular（400）、14px
Caption: Regular（400）、12px
```

---

## Component Stylings

### Button
```
Border radius:  8px
Padding:        12px 28px
Min width:      140px
Font weight:    SemiBold（600）
Font size:      16px
Transition:     all 0.15s ease

Primary button:
  background: #635BFF
  color: #FFFFFF
  box-shadow: 0 1px 3px rgba(99, 91, 255, 0.3)
  hover: background #7A73FF, box-shadow 0 4px 12px rgba(99, 91, 255, 0.35)

Secondary button:
  background: #FFFFFF
  border: 1px solid #E3E8EE
  color: #0A2540
  hover: border-color #635BFF, color #635BFF

Dark button:
  background: #0A2540
  color: #FFFFFF
  hover: background #1A3550
```

### Card
```
Border radius:  12px
Padding:        32px
Border:         1px solid #E3E8EE
Shadow:         0 2px 8px rgba(0, 0, 0, 0.06)
Background:     #FFFFFF
Hover shadow:   0 8px 24px rgba(0, 0, 0, 0.1)
Transition:     box-shadow 0.2s ease
```

### Input / Form
```
Border radius:  8px
Border:         1px solid #E3E8EE
Padding:        12px 16px
Font size:      16px
Background:     #FFFFFF
Focus outline:  2px solid #635BFF
Focus border:   1px solid #635BFF
Placeholder:    #8898AA
```

### Navigation
```
Height:         72px
Background:     #FFFFFF
Border-bottom:  1px solid #E3E8EE
Logo width:     100px
Link spacing:   40px
Link color:     #425466
Link hover:     #0A2540
Active link:    #635BFF
Backdrop-filter: blur(8px)（スクロール時）
```

### Code Block
```
Background:     #0A2540
Text:           #A3ACB9
Border radius:  8px
Padding:        24px
Font:           "SF Mono", "Fira Code", monospace
Font size:      14px
```

---

## Layout Principles

```
Max width:        1240px
Outer padding:    80px（モバイル: 24px）
Section spacing:  120px（セクション間の大きな余白で呼吸感を出す）
Grid columns:     12
Gutter:           32px
Hero height:      min 600px（ヒーローセクション）
```

**特徴的なレイアウトルール:**
- ヒーローセクションには微細なグラデーションメッシュ背景を使用
- コードブロックとUIプレビューを並列配置して「開発者体験」を伝える
- セクション間のスペースは贅沢に取り、情報密度を低く保つ

---

## Do's and Don'ts

### Do
- カラーパレット以外の色を使わない
- ボタンに微細な box-shadow を付けて浮遊感を出す
- コードスニペットにはダークテーマ（#0A2540背景）を使う
- 余白をたっぷり取り、1セクション1メッセージを守る
- 見出しには数字やメトリクスを含めて信頼感を出す
- グラデーションはブランドカラー付近の微妙な変化のみ許可（#635BFF → #7A73FF）
- ホバーアニメーションは0.15s〜0.2sの控えめなものにする

### Don't
- 派手なアニメーションやバウンスエフェクトを使わない
- テキストに影を付けない
- 1ページに3つ以上のCTAを配置しない
- アイコンに色を付けすぎない（モノトーンが基本）
- Surface色（#F6F9FC）の上にBorder色（#E3E8EE）のカードを置かない（コントラスト不足）
- フォントを3種類以上使わない（本文フォント＋コード用モノスペースのみ）

---

*Generated: 2026-04-10 — Stripe inspired design system*
