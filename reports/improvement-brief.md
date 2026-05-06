# WAN DELI 修正結果（文字被り解消優先）

## 原因
前回の95%比較で使った背景素材 `hero-bg-minimal-text-erased-1778081100.png` に、左側コピー・CTA・UIの残像が薄く焼き込まれていました。
その上にHTML/CSSの本物の文字を載せたため、**文字の上に文字が被る**状態になっていました。

## 修正
- 背景を完全に文字なしの素材へ差し替え。
- 採用背景: `assets/hero-bg-absolutely-textless-1778080468.png`
- 対象CSS: `style.css`, `style-goal-1778080789.css`

## 検証
- Chrome headlessでローカルPC表示を再撮影。
- 修正後スクショ: `reports/local-textless-pc.png`
- 比較画像: `reports/wan-deli-textless-fixed-comparison-pc.png`
- 数値JSON: `reports/textless-fixed-summary.json`

## 修正後の厳密比較
- 類似度: **90.30%**
- MAE: **24.73 / 255**
- 差分率: `>10 = 39.88%`, `>25 = 22.07%`, `>50 = 12.62%`

## 判断
95%スコアより、まず実サイトとして破綻していた文字被りを消すことを優先しました。
修正後は左側の見出し・説明文・CTA・バッジの上に、背景側の文字/UI残像はありません。

## 次の改善方針
ここから95%へ戻すには、**文字なしを絶対条件**にしたうえで右側ビジュアルだけをモックに近づける必要があります。
文字入り背景やUI残像つき背景は今後使いません。
