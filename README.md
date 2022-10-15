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

## git-flow をテストする

セットアップが完了したことを確認する為に `feature`の`test`ブランチを切ります。
以下のコマンドを実行します。

```bash
git flow feature start test
```

コマンドを実行すると以下のように実行結果が出力されます。

```txt
Switched to a new branch 'feature/test'

Summary of actions:
- A new branch 'feature/test' was created, based on 'develop'
- You are now on branch 'feature/test'

Now, start committing on your feature. When done, use:

     git flow feature finish test
```

`feature/test`ブランチが`develop`をベースに作成されます。

`test`ブランチの作業を完了する場合は以下のコマンドを実行します。

```bash
git flow feature finish test
```

コマンドを実行すると以下のように実行結果が出力されます。

```txt
Switched to branch 'develop'
Updating 74c9ab8..20e9cd7
Fast-forward
 README.md | 29 +++++++++++++++++++++++++++++
 1 file changed, 29 insertions(+)
Deleted branch feature/test (was 20e9cd7).

Summary of actions:
- The feature branch 'feature/test' was merged into 'develop'
- Feature branch 'feature/test' has been removed
- You are now on branch 'develop'
```

作業ブランチを完了するとdevelopブランチにスイッチして作業ブランチを自動で削除します。
