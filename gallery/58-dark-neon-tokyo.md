# DESIGN.md — ダークネオン東京

---

## Project Overview

- **Project Name**: ダークネオン東京 — 雨に滲むネオン
- **Vibe**: "東京の夜景。ピンク×ブルーのネオンが雨に濡れたアスファルトに反射する。サイバーでエモいUI"
- **Target User**: 音楽・ナイトライフ、ゲーム、クリエイティブポートフォリオ

---

## Color Palette & Roles

```
Primary:      #FF2D78   （メインCTA・ネオンピンク）
Secondary:    #00D4FF   （サブ・ネオンブルー）
Background:   #0D0221   （ページ背景・ディープパープル）
Surface:      #1A0A3E   （カード背景）
Text:         #E0D7FF   （本文テキスト・ラベンダー）
Text-muted:   #6B5B95   （補足テキスト）
Accent:       #00D4FF   （情報・リンク）
Border:       #2D1B69   （ボーダー）
```

---

## Typography Rules

```
Font:          "Inter", "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.6
H1: Bold 56px / H2: SemiBold 36px / H3: SemiBold 22px
```

---

## CSS / Component Examples

```css
/* ネオンピンクグロー */
.neon-pink {
  color: #FF2D78;
  text-shadow: 0 0 10px #FF2D78, 0 0 40px #FF2D78, 0 0 80px rgba(255, 45, 120, 0.4);
}

/* ネオンブルーグロー */
.neon-blue {
  color: #00D4FF;
  text-shadow: 0 0 10px #00D4FF, 0 0 40px #00D4FF;
}

/* ネオンボーダーカード */
.neon-card {
  background: rgba(26, 10, 62, 0.8);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 45, 120, 0.3);
  border-radius: 12px;
  padding: 28px;
  box-shadow: 0 0 20px rgba(255, 45, 120, 0.1), inset 0 0 20px rgba(0, 212, 255, 0.03);
}

/* 雨の反射エフェクト */
.rain-reflect {
  position: relative;
}
.rain-reflect::after {
  content: '';
  position: absolute;
  bottom: -100%;
  left: 0;
  right: 0;
  height: 100%;
  background: linear-gradient(to bottom, transparent, rgba(255, 45, 120, 0.05));
  transform: scaleY(-1);
  opacity: 0.3;
  filter: blur(4px);
  pointer-events: none;
}

/* ネオンボタン */
.neon-btn {
  background: transparent;
  border: 2px solid #FF2D78;
  color: #FF2D78;
  border-radius: 8px;
  padding: 14px 32px;
  box-shadow: 0 0 12px rgba(255, 45, 120, 0.4), inset 0 0 12px rgba(255, 45, 120, 0.1);
  transition: all 0.3s;
}
.neon-btn:hover {
  background: #FF2D78;
  color: #0D0221;
  box-shadow: 0 0 30px rgba(255, 45, 120, 0.6);
}
```

---

## Do's and Don'ts

### Do
- ネオングロー（text-shadow, box-shadow）をキーカラーに使う
- ダーク背景にネオンが「光る」表現を徹底
- backdrop-filterで奥行きを出す

### Don't
- 明るい背景にしない
- ネオンを3色以上同時に使わない
- グローを控えめにしすぎない（大胆に光らせる）

---

*Design Style: Dark Neon Tokyo — 2026-04-10*
