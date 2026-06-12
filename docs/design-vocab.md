# デザインを言葉で伝える

!!! info "この章のゴール"
    「こういう見た目にしたい」を、AIに伝わる**言葉**で表せるようになること。
    用語ごとに**実物のミニ見本**を並べたので、「これに近い」を選んで頼むだけでOKです。

<figure markdown="span">
  ![デザインを相談するイメージ](images/illustrations/design-tools.svg){ width="320" }
  <figcaption>「なんとなくおしゃれ」を、伝わる言葉に</figcaption>
</figure>

## なぜ「言葉」が大事？

**結論：AIは画面を“見て”いないので、雰囲気は言葉で伝える必要があります。**

**理由：** 「いい感じにして」だけだと、AIはどんな“いい感じ”か分かりません。
**「モダンで」「余白を広めに」「アクセントは青で」** のように、このページの言葉を添えると、ねらいに近づきます。

**具体例：**

```text
（×）おしゃれなトップ画面にして
（〇）モダンな雰囲気で、余白を広めに。アクセントカラーは青。
    上に大きめのヒーローを置いて、その下にカードを3つ並べて。
```

!!! warning "頼むときの注意"
    プロンプトに**実在の顧客名・案件名・社内システム名**などを書かないようにしましょう。
    見本やダミー名（`サンプル商店` など）で十分です。（→ [AIと安全に付き合う](ai-safety.md)）

<style>
/* === デザイン用語ミニ見本（このページ専用・dv- 接頭辞でスコープ）=== */
.dv-grid{display:flex;flex-wrap:wrap;gap:22px;margin:1.2em 0;}
.dv-item{width:240px;margin:0;}
.dv-item figcaption{font-size:.78rem;line-height:1.5;margin-top:.5em;color:var(--md-default-fg-color--light);}
.dv-item figcaption b{color:var(--md-default-fg-color);}
.dv-screen{width:240px;border-radius:11px;overflow:hidden;box-shadow:0 4px 16px rgba(0,0,0,.14);border:1px solid rgba(0,0,0,.08);background:#fff;font-family:system-ui,-apple-system,"Segoe UI",sans-serif;}
.dv-bar{height:22px;background:#f0f0f4;display:flex;align-items:center;gap:5px;padding:0 9px;}
.dv-bar i{width:8px;height:8px;border-radius:50%;background:#d2d2da;display:inline-block;}
.dv-page{padding:20px 18px;min-height:150px;display:flex;flex-direction:column;background:#fff;}
.dv-h{font-size:10px;font-weight:700;letter-spacing:.08em;margin-bottom:16px;color:#222;text-transform:uppercase;}
.dv-title{font-size:18px;font-weight:700;line-height:1.3;margin-bottom:9px;color:#1a1a1a;}
.dv-text{font-size:11px;color:#777;line-height:1.6;margin-bottom:16px;}
.dv-btn{align-self:flex-start;font-size:11px;padding:8px 16px;border-radius:7px;background:#333;color:#fff;font-weight:600;}

/* --- トーン別 --- */
.dv-modern .dv-btn{background:#4f46e5;border-radius:8px;}
.dv-modern .dv-h{color:#4f46e5;}

.dv-minimal .dv-page{background:#fff;}
.dv-minimal .dv-h{color:#999;font-weight:500;}
.dv-minimal .dv-title{font-weight:400;color:#111;letter-spacing:.02em;}
.dv-minimal .dv-btn{background:none;color:#111;border:1px solid #111;border-radius:0;font-weight:500;}

.dv-pop .dv-page{background:#fff7e6;}
.dv-pop .dv-h{color:#ff6f00;}
.dv-pop .dv-title{color:#ff3d81;}
.dv-pop .dv-btn{background:#ff3d81;border-radius:999px;font-weight:800;}

.dv-luxury .dv-bar{background:#23201c;}
.dv-luxury .dv-bar i{background:#544c3d;}
.dv-luxury .dv-page{background:#16130f;}
.dv-luxury .dv-h{color:#c9a96a;letter-spacing:.18em;}
.dv-luxury .dv-title{color:#ecdcb6;font-family:Georgia,"Times New Roman",serif;font-weight:500;}
.dv-luxury .dv-text{color:#a99c80;}
.dv-luxury .dv-btn{background:none;border:1px solid #c9a96a;color:#ecdcb6;border-radius:0;}

.dv-natural .dv-page{background:#f4efe4;}
.dv-natural .dv-h{color:#7c8a5f;}
.dv-natural .dv-title{color:#4c5a3a;}
.dv-natural .dv-text{color:#80795f;}
.dv-natural .dv-btn{background:#8a9a6b;border-radius:22px;}

.dv-retro .dv-page{background:#f6ead2;}
.dv-retro .dv-h{color:#b14a1f;letter-spacing:.1em;}
.dv-retro .dv-title{color:#c4561e;font-family:Georgia,serif;}
.dv-retro .dv-text{color:#8a6f4a;}
.dv-retro .dv-btn{background:#2e6068;border-radius:0;}

.dv-dark .dv-bar{background:#26262e;}
.dv-dark .dv-bar i{background:#444450;}
.dv-dark .dv-page{background:#1c1c22;}
.dv-dark .dv-h{color:#8b8bff;}
.dv-dark .dv-title{color:#f3f3f7;}
.dv-dark .dv-text{color:#9a9aa6;}
.dv-dark .dv-btn{background:#5b54f0;}

/* --- レイアウト用の部品 --- */
.dv-ly{padding:0;min-height:160px;}
.dv-block{background:#e3e3ee;border-radius:5px;}
.dv-accentblock{background:#4f46e5;}
.dv-hero{height:62px;background:linear-gradient(120deg,#5b54f0,#8b5cf6);display:flex;align-items:center;justify-content:center;color:#fff;font-size:12px;font-weight:700;}
.dv-pad{padding:12px;display:flex;flex-direction:column;gap:8px;}
.dv-row{display:flex;gap:8px;}
.dv-card{flex:1;height:46px;background:#eef0f7;border-radius:6px;border:1px solid #e0e2ee;}
.dv-line{height:8px;border-radius:4px;background:#e3e3ee;}
.dv-line.s{width:60%;}
.dv-cols{display:flex;height:160px;}
.dv-side{width:34%;background:#2b2b39;}
.dv-side .dv-line{background:#4a4a5e;margin:10px;}
.dv-main{flex:1;padding:12px;display:flex;flex-direction:column;gap:8px;}
.dv-gridcells{display:grid;grid-template-columns:1fr 1fr 1fr;gap:7px;padding:12px;}
.dv-cell{aspect-ratio:1;background:#eef0f7;border-radius:6px;border:1px solid #e0e2ee;}

/* --- 色 --- */
.dv-sw{display:flex;height:46px;border-radius:7px;overflow:hidden;margin-bottom:10px;}
.dv-sw span{flex:1;}
.dv-grad{height:46px;border-radius:7px;background:linear-gradient(120deg,#5b54f0,#ec4899);margin-bottom:10px;}

/* --- フォント比較 --- */
.dv-font{padding:18px;}
.dv-font .big{font-size:21px;font-weight:700;margin-bottom:4px;color:#1a1a1a;}
.dv-font .sml{font-size:11px;color:#777;}
.dv-gothic .big,.dv-gothic .sml{font-family:system-ui,"Hiragino Kaku Gothic ProN","Yu Gothic",sans-serif;}
.dv-mincho .big,.dv-mincho .sml{font-family:"Hiragino Mincho ProN","Yu Mincho",serif;}

/* --- ボタン見本 --- */
.dv-btns{padding:18px;display:flex;flex-direction:column;gap:11px;align-items:flex-start;}
.dv-b{font-size:11px;padding:8px 16px;font-weight:600;}
.dv-b.fill{background:#4f46e5;color:#fff;border-radius:7px;}
.dv-b.outline{background:none;color:#4f46e5;border:1px solid #4f46e5;border-radius:7px;}
.dv-b.pill{background:#4f46e5;color:#fff;border-radius:999px;}
.dv-b.square{background:#1a1a1a;color:#fff;border-radius:0;}
</style>

## 1. 全体の雰囲気・トーン

**同じ内容でも、トーンを変えるだけで印象がこんなに変わります**（下はすべて同じ「お店のトップ」の見本）。

<div class="dv-grid" markdown="0">

<figure class="dv-item">
  <div class="dv-screen dv-modern"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">Shop</div><div class="dv-title">あたらしい毎日を。</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>モダン</b><br>余白広め・無彩色＋1色・角丸ひかえめ。今っぽく洗練。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen dv-minimal"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">Shop</div><div class="dv-title">あたらしい毎日を。</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>ミニマル</b><br>色も飾りも極限まで削る。線は細く、白が主役。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen dv-pop"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">Shop</div><div class="dv-title">あたらしい毎日を！</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>ポップ</b><br>明るい色・丸み・元気。親しみやすく楽しい印象。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen dv-luxury"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">SHOP</div><div class="dv-title">あたらしい毎日を。</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>高級感／ラグジュアリー</b><br>暗い背景＋金・明朝。余白たっぷりで上質に。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen dv-natural"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">Shop</div><div class="dv-title">あたらしい毎日を。</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>ナチュラル</b><br>ベージュ・緑などの自然色。やわらかく落ち着く。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen dv-retro"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">SHOP</div><div class="dv-title">あたらしい毎日を。</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>レトロ</b><br>くすんだ色・昔っぽい配色。懐かしい雰囲気。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen dv-dark"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-h">Shop</div><div class="dv-title">あたらしい毎日を。</div><div class="dv-text">シンプルで使いやすい道具たち。</div><div class="dv-btn">見てみる</div></div></div>
  <figcaption><b>ダーク（ダークモード）</b><br>暗い背景＋明るい文字。目に優しく今っぽい。</figcaption>
</figure>

</div>

| 言葉 | こんな印象 | こう頼む |
|---|---|---|
| **モダン** | 洗練・今っぽい・すっきり | `モダンな雰囲気で` |
| **ミニマル** | 必要最小限・静か | `ミニマルに、要素を減らして` |
| **ポップ** | 明るい・楽しい・親しみ | `ポップで明るい感じ` |
| **高級感／ラグジュアリー** | 上質・落ち着き | `高級感のある雰囲気で` |
| **ナチュラル** | やわらかい・自然 | `ナチュラルで温かみのある色で` |
| **レトロ** | 懐かしい・味がある | `レトロな配色で` |
| **ダーク** | かっこいい・目に優しい | `ダークモードの配色で` |

## 2. レイアウト・構成

**画面のどこに何を置くか**を表す言葉です。「上にヒーロー、その下にカード3つ」のように組み合わせて伝えます。

<div class="dv-grid" markdown="0">

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-ly"><div class="dv-hero">大きな見出し</div><div class="dv-pad"><div class="dv-line"></div><div class="dv-line s"></div></div></div></div>
  <figcaption><b>ヒーロー</b><br>画面上部の大きな見せ場（写真や見出し）。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-ly"><div class="dv-pad"><div class="dv-row"><div class="dv-card"></div><div class="dv-card"></div><div class="dv-card"></div></div><div class="dv-row"><div class="dv-card"></div><div class="dv-card"></div><div class="dv-card"></div></div></div></div></div>
  <figcaption><b>カード</b><br>情報を四角いパネルに分けて並べる。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-ly"><div class="dv-gridcells"><div class="dv-cell"></div><div class="dv-cell"></div><div class="dv-cell"></div><div class="dv-cell"></div><div class="dv-cell"></div><div class="dv-cell"></div></div></div></div>
  <figcaption><b>グリッド</b><br>格子状に整然と並べる（写真一覧など）。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-ly"><div class="dv-cols"><div class="dv-side"><div class="dv-line"></div><div class="dv-line"></div><div class="dv-line s"></div></div><div class="dv-main"><div class="dv-line"></div><div class="dv-line s"></div><div class="dv-card" style="height:60px;"></div></div></div></div></div>
  <figcaption><b>サイドバー</b><br>横にメニュー列、残りが本文。管理画面に多い。</figcaption>
</figure>

</div>

| 言葉 | 意味 | こう頼む |
|---|---|---|
| **ヒーロー** | 上部の大きな見せ場 | `上に大きめのヒーローを置いて` |
| **カード** | 四角いパネルで区切る | `項目はカードで並べて` |
| **グリッド** | 格子状に整列 | `写真はグリッドで並べて` |
| **サイドバー** | 横のメニュー列 | `左にサイドバーメニューを` |
| **余白（ホワイトスペース）** | あえて空ける空間 | `余白を広めにとって、ゆったり` |

## 3. 色・配色

<div class="dv-grid" markdown="0">

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-line"></div><div class="dv-line s" style="margin-top:8px;margin-bottom:16px;"></div><div class="dv-btn" style="background:#4f46e5;">これだけ色</div></div></div>
  <figcaption><b>アクセントカラー</b><br>全体は無彩色、要所だけ1色効かせる。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-sw"><span style="background:#1a1a1a;"></span><span style="background:#5a5a5a;"></span><span style="background:#9a9a9a;"></span><span style="background:#d8d8d8;"></span></div><div class="dv-line"></div><div class="dv-line s" style="margin-top:8px;"></div></div></div>
  <figcaption><b>モノトーン</b><br>白〜黒の濃淡だけ。落ち着いて締まる。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page"><div class="dv-grad"></div><div class="dv-line"></div><div class="dv-line s" style="margin-top:8px;"></div></div></div>
  <figcaption><b>グラデーション</b><br>色をなめらかに変化。今っぽく華やか。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page" style="background:#111;"><div class="dv-title" style="color:#fff;">くっきり読める</div><div class="dv-text" style="color:#888;">背景と文字の明暗差が大きい状態。</div></div></div>
  <figcaption><b>コントラスト</b><br>明暗の差。大きいほど読みやすく目立つ。</figcaption>
</figure>

</div>

| 言葉 | 意味 | こう頼む |
|---|---|---|
| **アクセントカラー** | 要所に効かせる1色 | `アクセントカラーは青で` |
| **メインカラー／ベースカラー** | 全体の基調色／背景色 | `ベースは白、メインは紺で` |
| **モノトーン** | 白黒グレーだけ | `モノトーンでまとめて` |
| **グラデーション** | 色のなめらかな変化 | `見出しは青〜紫のグラデで` |
| **コントラスト** | 明暗・色の差 | `コントラスト高めで読みやすく` |

!!! tip "色は「名前」か「色コード」で"
    `青` のような言葉でも、`#1E88E5` のような**色コード（カラーコード）**でも伝えられます。
    ブランド色が決まっているなら、色コードを渡すと正確です。

## 4. 文字・フォント・部品

### 文字（フォント）の系統

<div class="dv-grid" markdown="0">

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-font dv-gothic"><div class="big">あたらしい毎日</div><div class="sml">線の太さが均一で、すっきり読みやすい。</div></div></div>
  <figcaption><b>ゴシック体（サンセリフ）</b><br>線が均一。現代的で画面向き。迷ったらこれ。</figcaption>
</figure>

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-font dv-mincho"><div class="big">あたらしい毎日</div><div class="sml">はらい・はねがあり、上品で落ち着く。</div></div></div>
  <figcaption><b>明朝体（セリフ）</b><br>線に強弱。上品・伝統的・読み物向き。</figcaption>
</figure>

</div>

### ボタンの形

<div class="dv-grid" markdown="0">

<figure class="dv-item">
  <div class="dv-screen"><div class="dv-bar"><i></i><i></i><i></i></div>
  <div class="dv-page dv-btns"><span class="dv-b fill">塗り（ベタ）</span><span class="dv-b outline">枠線だけ</span><span class="dv-b pill">角丸（ピル）</span><span class="dv-b square">角ばり</span></div></div>
  <figcaption><b>ボタンの種類</b><br>「塗り／枠線だけ／角丸／角ばり」で印象が変わる。</figcaption>
</figure>

</div>

| 言葉 | 意味 | こう頼む |
|---|---|---|
| **ゴシック体／サンセリフ** | 線が均一な文字 | `見出しはゴシックで` |
| **明朝体／セリフ** | 線に強弱がある文字 | `本文は明朝で上品に` |
| **塗りボタン** | 中まで色がある | `ボタンは塗りで目立たせて` |
| **枠線（アウトライン）ボタン** | 枠だけ | `サブのボタンは枠線だけで` |
| **角丸／ピル** | 角を丸める | `ボタンは角丸（ピル型）で` |
| **ナビ（ナビゲーション）** | 画面上の案内メニュー | `上にナビメニューを置いて` |

## 組み合わせて頼んでみる

言葉は**重ねるほど**ねらいに近づきます。

```text
ナチュラルな雰囲気のカフェのトップ画面を作って。
・上に大きめのヒーロー（お店の名前と一言）
・その下にメニューをカードで3つ
・ベースはベージュ、アクセントは深い緑
・見出しは明朝、ボタンは角丸
・余白は広めでゆったり
```

!!! tip "見本があるならそれが最速"
    「このサイトみたいにして」と、参考にしたいページの**URLやスクショ**を渡すのも有効です。
    そのうえで「ここの色だけ変えて」と言葉を足すと、より思い通りになります。

!!! warning "参考画像をそのまま使わない"
    気に入ったサイトの**画像やロゴをそのまま使う**のは、著作権・ライセンス上の問題になることがあります。
    「**雰囲気を参考に、中身は自分のものを作る**」のが安全です。

## この章のまとめ

- [x] 雰囲気は「モダン・ミニマル」などの**トーンの言葉**で伝えられる
- [x] 「ヒーロー・カード・サイドバー」など**レイアウトの言葉**が分かった
- [x] 色は**言葉か色コード**で、アクセント／コントラストを指定できる
- [x] プロンプトに**実在の顧客名・機密**は書かない

!!! success "次のステップ"
    言葉がそろったら、実際に作ってみましょう。
    👉 [AIで作ってみる（ハンズオン）](ai-build.md)
