# Step 1 / Step 2: MOCK vs LATEST 差分整理

## Step 1: 差分箇条書き
- 犬・商品写真: LATESTは犬の顔位置がMOCKよりわずかに右/下へ見え、商品群の下端・右側ボトルの入り方もMOCKとズレている。全体に少し白く、商品周辺の奥行きが弱い。
- 右上カード: LATESTはカードがMOCKよりやや小さく、影が軽い。人気No.1カード内の商品写真も小さく見え、カード間隔/右位置が微妙に違う。
- ヘッダー: LATESTはロゴ、ナビ、右アイコン群がMOCKより細く小さく見える。ヘッダー全体の密度が少し軽い。
- CTAボタン: LATESTは高さ・横幅・影の存在感が少し弱く、MOCKより押せるUIとして軽く見える。
- バッジ/安心バー: LATESTは下部要素が細かく分散して見え、MOCKのまとまった白いバー感より薄い。アイコン/文字サイズと余白も少し弱い。
- 色味/白さ: LATESTは全体的に白く、MOCKの温かいベージュ感・背景の奥行きが少し不足。

## Step 2: 修正方法の切り分け
### CSSで直す箇所
- header高さ、ロゴサイズ、nav gap/font-size、右アイコンサイズ/間隔
- h1/leadのサイズ・行間・位置
- CTAのheight/min-width/padding/shadow/gap
- cardのwidth/min-height/top/right/padding/radius/shadow、内部商品写真サイズ
- badge/campaign/trust-barのheight/width/gap/icon/textサイズ/影
- overlay/filter/card backgroundで白さ・温かさを微調整

### 画像表示位置で直す箇所
- .hero-photo の background-position / background-size / filter
- 犬の顔中心、商品パッケージ高さ、右側スプレーボトルの見え方
