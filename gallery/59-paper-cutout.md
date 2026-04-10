# DESIGN.md — ペーパーカットアウト

---

## Project Overview

- **Project Name**: ペーパーカットアウト — 切り紙コラージュ
- **Vibe**: "レイヤードな紙の影が奥行きを作る。手作り感とクラフト的な温もりのデザイン"
- **Target User**: 教育、クラフト、ハンドメイド、子供向け

---

## Color Palette & Roles

```
Primary:      #E74C3C   （メインCTA・レッド）
Secondary:    #3498DB   （サブ・ブルー）
Background:   #FDF6E3   （ページ背景・クラフト紙）
Surface:      #FFFFFF   （カード・白い紙）
Text:         #2C3E50   （本文テキスト）
Text-muted:   #7F8C8D   （補足テキスト）
Accent:       #F39C12   （イエロー・マスキングテープ）
Border:       none
```

---

## Typography Rules

```
Font:          "Nunito", "Noto Sans JP", sans-serif
Base size:     16px
Line height:   1.7
H1: Bold 40px / H2: Bold 28px / H3: SemiBold 20px
```

---

## CSS / Component Examples

```css
/* ペーパーカード（重ねた紙） */
.paper-card {
  background: #fff;
  border-radius: 4px;
  padding: 32px;
  position: relative;
  box-shadow:
    0 1px 3px rgba(0,0,0,0.08),
    0 4px 8px rgba(0,0,0,0.06),
    0 12px 24px rgba(0,0,0,0.04);
}
/* 下に重なった紙 */
.paper-card::before {
  content: '';
  position: absolute;
  top: 4px; left: 4px; right: -4px; bottom: -4px;
  background: #F0E6D4;
  border-radius: 4px;
  z-index: -1;
  transform: rotate(1deg);
}
.paper-card::after {
  content: '';
  position: absolute;
  top: 8px; left: -2px; right: 6px; bottom: -8px;
  background: #E8DCC8;
  border-radius: 4px;
  z-index: -2;
  transform: rotate(-1.5deg);
}

/* マスキングテープ */
.tape {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%) rotate(-2deg);
  width: 80px;
  height: 24px;
  background: rgba(243, 156, 18, 0.6);
  border-radius: 1px;
}

/* 破れた紙の縁 */
.torn-edge {
  position: relative;
}
.torn-edge::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 20px;
  background: url("data:image/svg+xml,%3Csvg viewBox='0 0 100 20' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0 10 Q5 0 10 8 Q15 16 20 6 Q25 0 30 10 Q35 18 40 8 Q45 2 50 10 Q55 16 60 4 Q65 0 70 12 Q75 18 80 6 Q85 0 90 10 Q95 16 100 8 V20 H0 Z' fill='%23FDF6E3'/%3E%3C/svg%3E") repeat-x;
  background-size: 100px 20px;
}
```

---

## Do's and Don'ts

### Do
- box-shadowを重ねて紙の重なりを表現
- 微妙なrotateで手作り感を出す
- マスキングテープやピンなどの装飾を添える

### Don't
- 影を1つだけにしない（重ねることで立体感）
- 完全な直線・完全な整列にしない（微妙にずらす）
- 角丸を大きくしすぎない（紙は角ばっている）

---

*Design Style: Paper Cutout — 2026-04-10*
