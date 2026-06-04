# PCの準備（VSCode・Git・Claude）

!!! info "この章のゴール"
    自分のPCに **VSCode**・**Git**・**Claude** を入れて、
    「GitHubの操作を、画面の案内とClaudeへのお願いで進められる」状態にすること。

<figure markdown="span">
  ![アプリをインストールするイメージ](images/illustrations/app-installation.svg){ width="320" }
  <figcaption>必要な道具を順番にそろえていきます</figcaption>
</figure>

## このガイドの進め方（VSCode＋Claude）

このあとの章では、GitHubの操作を次の **2通り** で並べて説明します。好きな方を選んでください。

- :material-robot-happy-outline: **Claudeに頼む** … VSCodeの中で、Claudeに日本語でお願いする（コマンド不要）
- :material-cursor-default-click-outline: **自分で操作** … 画面のボタンを自分でクリックする

```mermaid
flowchart LR
    A[1.VSCode<br/>編集ソフト] --> B[2.Git<br/>履歴の仕組み]
    B --> C[3.GitHubに接続<br/>サインイン]
    C --> D[4.Claude<br/>お願いできる相棒]
    D --> E([準備完了 🎉])
```

!!! tip "全部入れるのが大変なときは"
    まずは **VSCode** と **Git** だけでも大丈夫です。Claudeは後からでも追加できます。

---

## 1. VSCode（ブイエスコード）を入れる

VSCodeは、**文章やファイルを編集できる無料のソフト**です。GitHubとの相性がよく、初心者にもおすすめです。

公式サイト [https://code.visualstudio.com](https://code.visualstudio.com) を開き、自分のPCに合うボタンから入れます。

=== ":material-microsoft-windows: Windows"

    1. 公式サイトの **Download for Windows** を押す
    2. ダウンロードされたファイル（`...User Setup.exe`）を開く
    3. 画面の案内に従って「次へ」で進める（途中の同意・追加タスクはそのままでOK）
    4. 完了したらVSCodeを起動する

=== ":material-apple: Mac"

    1. 公式サイトの **Download for Mac** を押す
    2. ダウンロードされた `.zip` を開くと、`Visual Studio Code` アプリが出てくる
    3. それを **アプリケーション** フォルダにドラッグして移動する
    4. アプリケーションから起動する

!!! quote "📷 画面キャプチャ枠（あとで差し込み）"
    VSCode公式サイトのダウンロードボタンの画面を入れます。
    `![VSCodeのダウンロード画面](images/setup-01-vscode.png){ width="700" }`

!!! tip "日本語表示にする"
    初回起動時に「日本語に変更しますか？」と出たら **「インストールして再起動」** を押すと、メニューが日本語になります。

---

## 2. Git（ギット）を入れる

Gitは、**変更の履歴を管理する“仕組み”そのもの**です（→ [用語集](glossary.md)）。GitHubを使うPCに必要です。

=== ":material-microsoft-windows: Windows"

    1. [https://git-scm.com/download/win](https://git-scm.com/download/win) を開く
    2. 自動でダウンロードが始まる（始まらなければ案内のリンクを押す）
    3. ファイルを開き、画面の案内は **基本そのまま「Next」** で進めてOK
    4. 「Install」→「Finish」で完了

=== ":material-apple: Mac"

    Macは最初からGitが入っていることが多いです。まず確認します。

    1. **VSCodeを開く** → メニューの「ターミナル」→「新しいターミナル」
    2. 次の1行を貼り付けて Enter

        ```bash
        git --version
        ```

    3. `git version 2.xx.x` のように出れば、すでに入っています
    4. 入っていない場合は、案内ウィンドウが出るので **「インストール」** を押す

!!! note "確認だけなら覚えなくてOK"
    `git --version` は「入っているか確かめる」ためのものです。意味を覚える必要はありません。

---

## 3. VSCodeからGitHubにサインインする

VSCodeと、前章で作った **GitHubアカウント** をつなぎます。これで「自分のGitHub」とやりとりできます。

```mermaid
flowchart LR
    A[VSCode左下の<br/>アカウントアイコン] --> B["Sign in with GitHub<br/>を選ぶ"]
    B --> C[ブラウザでGitHubに<br/>ログイン＆許可]
    C --> D([接続完了 ✅])
```

!!! quote "📷 画面キャプチャ枠（あとで差し込み）"
    VSCode左下のアカウントアイコンからサインインする画面を入れます。
    `![GitHubへのサインイン](images/setup-02-signin.png){ width="700" }`

---

## 4. Claude（クロード）を入れる

<figure markdown="span">
  ![相棒となるツールを使うイメージ](images/illustrations/design-tools.svg){ width="320" }
  <figcaption>「○○して」とお願いすると、操作を手伝ってくれます</figcaption>
</figure>

Claudeは、**VSCodeの中で日本語でお願いできるAIの相棒**です。
「新しいリポジトリを作って」「この変更を記録して」のように頼むと、操作を代わりに進めてくれます。

導入のおおまかな流れ：

1. VSCodeの左側の **拡張機能（四角が4つのアイコン :material-puzzle-outline:）** を開く
2. 検索欄に **`Claude`** と入力する
3. 表示された拡張機能を **インストール（Install）** する
4. 画面の案内に従って、Claudeのアカウントでサインインする

!!! tip "Node.js などの事前準備は不要です"
    Claude Code の VSCode拡張には、必要なもの（CLI）が **内蔵** されています。
    そのため **Node.js のインストールは不要** です。拡張を入れてサインインすれば、すぐ使えます。
    （`npm install` でCLIを入れる方法だけは Node.js が必要ですが、拡張を使うなら関係ありません。）

!!! info "正確な手順は公式案内を確認"
    Claudeの導入方法は更新されることがあります。最新の手順は、社内の案内または公式ドキュメントを確認してください。
    （会社で配布・利用ルールがある場合は、それに従ってください。）

!!! quote "📷 画面キャプチャ枠（あとで差し込み）"
    拡張機能で「Claude」を検索した画面を入れます。
    `![Claude拡張のインストール](images/setup-03-claude.png){ width="700" }`

### :material-console: ターミナルでも使う：CLI版（任意）

VSCodeの拡張だけで十分な人は、ここは **飛ばしてOK** です。
ターミナルから `claude` を直接使いたい人向けに、CLI版も入れられます（**Node.js は不要**）。

=== ":material-apple: Mac / Linux"

    ```bash
    curl -fsSL https://claude.ai/install.sh | bash
    ```

=== ":material-microsoft-windows: Windows（PowerShell）"

    ```powershell
    irm https://claude.ai/install.ps1 | iex
    ```

入れたら、ターミナルで `claude` と打って起動し、初回は画面の案内に従ってログインします。

!!! note "Node.js で入れる方法もある"
    すでに Node.js（18以上）がある人は `npm install -g @anthropic-ai/claude-code` でも入れられます。どれか1つの方法でOKです。

---

## :material-console: GitHub CLI（gh）を入れる（GitHub操作におすすめ） { #github-cli-gh }

GitHub CLI（`gh`）は、GitHubの操作（**リポジトリ作成・プルリク作成** など）を行うための道具です。

!!! info "実は「Claudeに頼む」ときも使われます"
    Claudeにリポジトリ作成やプルリク作成を頼むと、Claudeは **内部でこの `gh` コマンドを使います**。
    そのため、Claudeで進める人も `gh` を入れておくとスムーズです（未導入だと、これらの操作でつまずくことがあります）。

    - **コミット・プッシュ** だけなら `git`（前の手順で導入済み）でOK ― `gh` は不要です
    - **リポジトリ作成・プルリク作成** など“GitHub側”の操作で `gh` が活躍します
    - **GitHubサイト（ブラウザ）だけ** で操作するなら、`gh` がなくても大丈夫です

### いちばん簡単：Claudeに頼む

VSCodeのClaudeに、こう頼むだけでOKです。

```text
GitHub CLI（gh）を入れて、GitHubにログインできるようにして。
```

Claudeが、お使いのPCに合った方法でインストールから初期設定（ログイン）まで進めてくれます。
（Homebrewなどの準備が必要な場合も、まとめてやってくれます。）

### 自分で入れる場合

=== ":material-microsoft-windows: Windows"

    PowerShell などで次を実行します。

    ```powershell
    winget install --id GitHub.cli
    ```

    うまくいかないときは [cli.github.com](https://cli.github.com) のインストーラーからでも入れられます。

=== ":material-apple: Mac"

    [Homebrew](https://brew.sh) が入っていれば、次の1行で入ります。

    ```bash
    brew install gh
    ```

    !!! note "Homebrew が入っていないとき"
        Homebrew は、Macでソフトを入れるための定番ツールです。
        未導入なら [brew.sh](https://brew.sh) の手順で入れるか、**Claudeに「Homebrewを入れて」と頼む** のが簡単です。
        （`gh` の導入ごとClaudeに頼めば、必要な準備もまとめてやってくれます。）

入れたら、GitHubと接続（ログイン）します。

```bash
gh auth login
```

画面の質問に **↑↓ と Enter** で答えていきます（迷ったら `GitHub.com` → `HTTPS` → ブラウザで認証、の順で選べばOK）。

!!! tip "入っているか確認"
    `gh --version` でバージョンが表示されれば準備完了です。
    入れ方に迷ったら、Claudeに「`gh` を使えるようにして」と頼むこともできます。

---

## この章のまとめ

```mermaid
flowchart LR
    A[VSCode] --> B[Git]
    B --> C[GitHubに接続]
    C --> D[Claude]
    D --> E([準備完了 🎉])
```

- [x] VSCodeを入れた
- [x] Gitを入れた
- [x] VSCodeからGitHubにサインインした
- [x] Claudeを入れた（後回しでもOK）

!!! success "次のステップ"
    道具がそろいました。さっそく、自分のファイル置き場（リポジトリ）を作ってみましょう。

    👉 [最初の一歩（リポジトリを作る）](first-steps.md)
