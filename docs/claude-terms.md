# Claudeの用語集

Claude（特に **Claude Code**）を使うときに出てくる言葉を、身近なたとえで説明します。
パソコン全般の言葉は [基本のIT用語集](it-basics.md) にまとめています。

!!! tip "読み方"
    全部を覚える必要はありません。「こんな感じ」とイメージがつかめれば十分です。
    分からない言葉が出てきたら、このページに戻ってきてください。

---

## :material-star-four-points-outline: Claude Codeの主な機能

### :material-slash-forward-box: コマンド（command／スラッシュコマンド）
**`/`（スラッシュ）から始めて呼び出す、決まった機能や定型の指示** です。例：`/help`。
よく使う手順を **自分で登録して呼び出す** こともできます。

> ⌨️ たとえ：メニューから「いつもの操作」をワンタップで呼び出すイメージ。

### :material-toolbox-outline: スキル（skill）
**ある作業の「やり方・専門知識」をひとまとめにしたもの** です。Claudeが必要なときに読み込んで使います。`/スキル名` で自分から呼び出せるものもあります。

> 📚 たとえ：特定作業の「専門家の手順書」。渡しておくと、その道のやり方で進めてくれる。

### :material-account-multiple-outline: エージェント（agent／サブエージェント）
**本体のClaudeとは別に、独立した作業スペースで仕事を任せる“分身”** です。複数を **並行で動かして手分け** できます。

> 🤝 たとえ：本体の代わりに調べ物や作業を任せる「アシスタント」。何人かに同時に頼める。

!!! note "3つの関係"
    ざっくり言うと、**コマンド＝呼び出し方**、**スキル＝やり方の知識**、**エージェント＝作業を任せる相手**。
    「`/スキル名` で呼ぶ」「重い作業はエージェントに任せる」のように組み合わせて使います。

---

## :material-cog-outline: 仕組み・設定

### :material-power-plug-outline: MCP（エム・シー・ピー）
**Claudeを外部のツールやデータ（Google Drive・Backlogなど）につなぐための共通の仕組み** です（Model Context Protocol）。

> 🔌 たとえ：いろいろな道具を差し込める「共通コンセント」。

### :material-file-document-outline: CLAUDE.md（クロード・エムディー）
**プロジェクトのルールや前提を書いておく設定ファイル** です。Claudeが毎回読んで、それに沿って作業します。

> 📖 たとえ：チームの「作業ルールブック」。最初に渡しておく約束事。

### :material-hook: フック（hook）
**決めたタイミング（作業の前後など）で自動的に処理を走らせる設定** です。

> ⚙️ たとえ：「○○したら自動で△△する」という仕掛け。

### :material-shield-check-outline: 権限（permission／許可）
**Claudeがコマンド実行やファイル編集をする前に「やっていい？」と確認する仕組み** です。許可の範囲を設定できます。

> ✋ たとえ：作業前の「これ、進めていいですか？」の確認。

### :material-clipboard-list-outline: プランモード（Plan Mode）
**すぐ実行せず、まず計画を立てて見せ、承認をもらってから進めるモード** です。

> 🗺️ たとえ：着工前に「工程表」を見せて確認してもらうイメージ。

### :material-brain: メモリ（Memory）
**会話をまたいで覚えておく仕組み** です。好みや前提を記憶して、次回以降に活かします。

> 🧠 たとえ：担当者が「引き継ぎメモ」を残しておくイメージ。

---

## :material-robot-outline: AIの基礎

### :material-message-text-outline: プロンプト（Prompt）
**Claudeへの指示・お願いの文** です。**具体的に伝えるほど、良い結果**につながります。

> 📝 たとえ：仕事の「依頼文」。書き方のコツは [付録：Claudeの頼み方](appendix.md) を参照。

### :material-robot-happy-outline: モデル（Model）
**Claudeの種類** です。用途で選びます。

- **Opus** … 高性能（むずかしい作業向き）
- **Sonnet** … バランス型（ふだん使い）
- **Haiku** … 軽快・高速（かんたんな作業向き）

> 🚗 たとえ：目的で選ぶ「車種（速さ・パワーの違い）」。

### :material-circle-multiple-outline: トークン（Token）
**AIが文章を扱うときの細かい単位** です。長さや料金の **目安** になります。

> 📏 たとえ：文章を測る「文字数のような単位」。

### :material-text-box-outline: コンテキストウィンドウ（Context Window）
**Claudeが一度に覚えていられる範囲** です。会話が長くなると、古い部分は **自動で要約** されます。

> 🗃️ たとえ：机に一度に広げられる「書類の量の上限」。

### :material-head-question-outline: ハルシネーション（Hallucination）
**AIが、もっともらしいけれど誤った内容を言ってしまうこと** です。**大事な内容は必ず裏取り** を。

> 💭 たとえ：自信満々の「うろ覚え発言」。うのみにしない。

---

## :material-connection: 使い方・連携

### :material-laptop: Claude Code と :material-web: Web版（claude.ai）の違い
- **Claude Code** … PC上で **コードやファイルを直接触れる**、開発者向けの使い方（VSCode拡張やターミナル）。
- **Web版（claude.ai）** … ブラウザで **会話する** 一般的な使い方。

> 🛠️💬 たとえ：現場で手を動かす「作業モード（Code）」と、相談する「会話モード（Web）」。

### :material-console: ターミナル版（CLI）
**ターミナルから `claude` コマンドで起動するClaude Code** です。VSCode拡張のほか、こちらでも使えます。

> ⌨️ たとえ：画面のボタンではなく、文字で呼び出す起動のしかた（→ [基本のIT用語集](it-basics.md)のCUI）。

### :material-card-account-details-outline: サブスクリプション（Pro・Max など）
**月額で使えるプラン** です。プランによって使用量の上限などが異なります。

> 🎫 たとえ：使い放題の度合いが違う「月額パス」。

### :material-api: API連携
**自分のアプリやツールから、プログラムでClaudeを呼び出す使い方** です。利用には **APIキー** が必要です。

!!! warning "APIキーの扱いに注意"
    APIキーは秘密のカギです。**コードに直接書かない／画面に貼らない**、実在の顧客名・案件名や認証情報を渡さないよう気をつけてください（→ [AIと安全に付き合う](ai-safety.md)）。

---

!!! note "関連する用語集"
    - パソコン全般の言葉 → [基本のIT用語集](it-basics.md)
    - Git/GitHub特有の言葉 → [GitHubの用語集](glossary.md)
    - Claudeへの上手な頼み方 → [付録：Claudeの頼み方とMarkdown](appendix.md)

言葉のイメージがつかめたら、[AIで開発するとは](ai-intro.md) に戻って全体の流れを確認してみましょう。
