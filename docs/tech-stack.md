# 推奨技術スタック

!!! info "このページのゴール"
    新しくWebアプリを作るときの **標準の道具（技術スタック）** をそろえて知ること。
    「何を・なぜ選ぶのか」を共有し、迷わず開発を始められるようにします。

<figure markdown="span">
  ![整理された技術選定のイメージ](images/illustrations/organizing-projects.svg){ width="320" }
  <figcaption>道具を決めておくと、毎回の「何を使う？」で迷いません</figcaption>
</figure>

!!! tip "AIに頼むときにも役立ちます"
    Claudeに開発を頼むとき、**「このスタックで作って」** と最初に伝えると、社内の標準に沿ったコードを出してもらいやすくなります。
    例：「pnpm + TanStack Start + drizzle-orm + PostgreSQL で作って」

!!! note "これは『新規プロジェクトの初期値』です"
    すべてのプロジェクトを今すぐ揃える必要はありません。**新しく作るとき** の出発点としてください。
    案件の事情（客先の指定など）で変える場合は、チームで相談のうえ判断します。

---

## 全体の早見表

| カテゴリ | 採用技術 | ひとことで言うと |
|---|---|---|
| パッケージマネージャー | **pnpm** | 速い・容量を節約・安全 |
| フルスタックフレームワーク | **TanStack Start** | 型安全＋高速＋デプロイ自由 |
| 認証 | **better-auth** | 二要素認証まで対応 |
| ORM（DB操作） | **drizzle-orm** | SQLの知識をそのまま活かせる |
| UIコンポーネント | **ark-ui** | 見た目を自由に作れる（色味カスタムに強い） |
| CSS | **Tailwind CSS** ＋ **Tailwind Variants** | クラスで素早くスタイリング |
| バリデーション | **zod** | 入力チェックを型と一緒に |
| ビルドツール | **Vite** | 開発も本番も高速 |
| テスト | **Vitest** | Viteと同じ仕組みで軽快 |
| データベース | **PostgreSQL** | 定番で堅牢なDB |
| リバースプロキシ | **nginx** | 入口の振り分け役 |
| メール | **docker-mailserver** | 自前のメール基盤をコンテナで |

---

## :material-content-copy: そのままClaudeに貼れる定型文

右上の :material-content-copy: ボタンでコピーして、Claudeへの最初のメッセージに貼ってください。
**「何を作りたいか」を1行目に書き足す** と、社内標準のスタックに沿って作ってもらえます。

```text
これから新規Webアプリを作ります。次の技術スタックで進めてください。

【作りたいもの】
（ここに作りたいものを書く。例：問い合わせフォーム付きの社内向けダッシュボード）

【技術スタック（社内標準）】
- パッケージマネージャー: pnpm
- フルスタックフレームワーク: TanStack Start（型安全ルーティング / Viteベース）
- ビルドツール: Vite
- UIコンポーネント: ark-ui
- CSS: Tailwind CSS + Tailwind Variants
- バリデーション: zod
- 認証: better-auth（二要素認証を使う）
- ORM: drizzle-orm
- データベース: PostgreSQL
- テスト: Vitest
- リバースプロキシ: nginx
- メール: docker-mailserver

【お願い】
- まず全体構成（フォルダ/ファイルの方針）を提案してから、小さく動くものを作ってください。
- 認証情報（パスワード・APIキー等）はコードに直書きせず、環境変数の使い方も教えてください。
- 進め方や不明点があれば、作り始める前に質問してください。
```

!!! tip "短く頼みたいとき"
    1行で済ませたい場合はこれだけでもOKです。

    ```text
    pnpm + TanStack Start + ark-ui + Tailwind CSS + drizzle-orm + PostgreSQL + zod + better-auth + Vite + Vitest で作って。
    ```

!!! warning "貼る前の確認"
    定型文に **実在の顧客名・案件名や認証情報** を書き込まないでください（→ [AIと安全に付き合う](ai-safety.md)）。

---

## フロントエンド・アプリ基盤

### :material-application-braces: フルスタックフレームワーク：TanStack Start

**結論：新規Webアプリの土台は TanStack Start を標準にします。**

**理由（採用ポイント）：**

- :material-shield-check: **型安全ルーティング** — ページ間のリンクやパラメータの間違いを、書いた時点で気づける
- :material-rocket-launch: **Viteベースで高速な開発体験** — 保存するとすぐ画面に反映される
- :material-cloud-cog: **デプロイ先の柔軟性** — 特定のサービスに縛られず、置き場所を選べる

### :material-vuetify: ビルドツール：Vite

**結論：ビルド・開発サーバーは Vite を使います。**

- 開発中の表示が速く、待ち時間が少ない
- TanStack Start も Vitest も Vite を土台にしており、**道具がそろう** のが大きな利点

### :material-palette-swatch: UIコンポーネント：ark-ui

**結論：UIの部品は ark-ui を標準とします。**

**理由：**

- :material-format-color-fill: **見た目（色・形）を自由に作れる** ヘッドレス設計。客先オリジナルの色味でも、デザインに素直に合わせられる
- :material-tailwind: 後述の **Tailwind CSS / Tailwind Variants と相性が良い**

!!! note "shadcn/ui を見送った経緯と再評価について"
    shadcn/ui は、**評価したタイミングが Tailwind CSS v4 への対応が不十分なころ** だったため、いったん見送りました。
    また、**客先オリジナルの色味** を使う案件では、最初からスタイルが付いている shadcn/ui の利点が大きく減ります（自分で色を上書きする手間が増える）。

    現在は v4 対応が進んでいるため、**標準色ベースの案件では再評価の余地あり**。ただし「色味のカスタムが多い案件 → ark-ui」という現状の使い分けは引き続き有効です。

### :material-language-css3: CSS：Tailwind CSS ＋ Tailwind Variants

**結論：スタイリングは Tailwind CSS を基本に、出し分けは Tailwind Variants で整理します。**

- **Tailwind CSS**：クラスを付けるだけで素早くスタイルを当てられる
- **Tailwind Variants**：「サイズ大/小」「色：青/赤」などの **見た目のパターンを型安全に管理** できる

---

## データ・バックエンド

### :material-database-cog: ORM：drizzle-orm

**結論：データベース操作は drizzle-orm を標準にします。**

**理由：**

- :material-database-search: **SQLの知識がそのまま活かせる** — SQLに近い書き心地で、学習コストが低い
- :material-speedometer: **SQLのパフォーマンスを良くできる** — 発行されるクエリが見えやすく、無駄な処理を抑えやすい

### :material-elephant: データベース：PostgreSQL

**結論：DBは PostgreSQL を標準とします。**

- 実績が豊富で堅牢、機能も充実した定番のリレーショナルDB
- drizzle-orm との組み合わせで安心して使える

### :material-shield-key: 認証：better-auth

**結論：ログイン・認証まわりは better-auth を使います。**

- :material-cellphone-key: **二要素認証（2FA）に対応** — パスワードに加えてもう一段の確認ができ、安全性を高められる

!!! warning "認証情報の扱いに注意"
    パスワード・APIキー・トークンなどの認証情報は、**コードに直接書かない／AIに渡さない** のが基本です（→ [AIと安全に付き合う](ai-safety.md)）。

### :material-check-decagram: バリデーション：zod

**結論：入力チェック（バリデーション）は zod で行います。**

- 「必須」「メール形式」などの **入力ルールを型と一緒に定義** できる
- フォーム・APIの両方で、不正な値が入り込むのを防げる

---

## 開発まわり

### :material-package-variant-closed: パッケージマネージャー：pnpm

**結論：ライブラリの管理は pnpm を標準にします。**

**理由：**

- :material-harddisk: **ディスク容量の削減** — 同じライブラリを共有して保存するため、PCの容量を節約できる
- :material-security: **サプライチェーン攻撃対策** — インストールの仕組みが厳格で、意図しないコードの混入リスクを抑えやすい

!!! tip "サプライチェーン攻撃って？"
    ライブラリ（部品）に悪意のあるコードを紛れ込ませて攻撃する手口のこと。
    pnpm は依存関係を厳密に扱うため、こうしたリスクを減らすのに役立ちます。

### :material-test-tube: テスト：Vitest

**結論：自動テストは Vitest で書きます。**

- Vite と同じ仕組みで動くため、**設定が少なく軽快**
- 開発で使う道具とそろっているので、学ぶことが減る

---

## インフラ・運用

### :material-arrow-decision: リバースプロキシ：nginx

**結論：サーバーの入口（振り分け役）は nginx を使います。**

- 外からのアクセスを受け取り、適切なアプリへ **振り分ける**
- HTTPS化や静的ファイルの配信など、入口まわりの役割を担う

### :material-email-fast: メール：docker-mailserver

**結論：メール基盤は docker-mailserver で構築します。**

- メールの送受信に必要な機能を **コンテナ（Docker）でまとめて** 用意できる
- 環境を再現しやすく、構築・移行がしやすい

---

## このページのまとめ

- [x] 新規プロジェクトの **標準スタック** が一覧で分かる
- [x] それぞれ **なぜ選ぶのか（理由）** が共有できる
- [x] AIに頼むときも「このスタックで」と伝えれば、社内標準に沿いやすい

!!! success "次のステップ"
    使う道具が決まったら、実際に手を動かしてみましょう。

    👉 [AIで作ってみる（ハンズオン）](ai-build.md)
