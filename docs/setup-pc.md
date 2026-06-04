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

!!! info "正確な手順は公式案内を確認"
    Claudeの導入方法は更新されることがあります。最新の手順は、社内の案内または公式ドキュメントを確認してください。
    （会社で配布・利用ルールがある場合は、それに従ってください。）

!!! quote "📷 画面キャプチャ枠（あとで差し込み）"
    拡張機能で「Claude」を検索した画面を入れます。
    `![Claude拡張のインストール](images/setup-03-claude.png){ width="700" }`

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
