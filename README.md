# gitflow-beginner

git-flow に入門する

## git-flow のセットアップ

### git-flow をインストールする

`git-flow`をインストールをする為に以下のコマンドを実行します。

```bash
brew install git-flow
```

### git-flow を初期化する

`git-flow`の設定を初期化する為に以下のコマンドを実行します。

```bash
git flow init
```

強制的に初期化する場合は `-f` をオプションとしてつけます。

```bash
git flow init -f
```

※ステージングしていない変更があると`git-flow`は初期化はできません。

```txt
fatal: Working tree contains unstaged changes. Aborting.
```

### git-flow を設定する

`git-flow` を実行後、対話形式で設定に関する質問がなされます。
以下のように設定します。

|項目|設定値|説明|
|:---|:---|:---|
|Branch name for production releases|main|リリース用のブランチ名|
|Branch name for "next release" development|develop|開発用のブランチ名|
|Feature branches?|feature/|作業用ブランチ名のプレフィックス|
|Release branches?|release/|リリース用ブランチ名のプレフィックス|
|Hotfix branches?|hotfix/|hotfix||
|Support branches?|support/|support||
|Version tag prefix?|tag|tag|
