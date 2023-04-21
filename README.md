# Git Document

![github](/images/github.webp)

[![giticon](https://skillicons.dev/icons?i=git,github)](https://skillicons.dev)

## 目次

編集した

- チェック

  - [説明](/EXPLANATION.md)
  - [git 勉強に](/TEST.md)

- コマンド
  - [version](#version)
  - [init](#init)
  - [pull](#pull)
  - [push](#push)
  - [add](#add)
  - [commit](#commit)
  - [reset](#reset)
  - [revert](#revert)
  - [log](#log)
  - [tag](#tag)
  - [status](#status)
  - [diff](#diff)
  - [stash](#stash)
  - [branch](#branch)
  - [checkout](#checkout)
  - [switch](#switch)
  - [merge](#merge)
  - [remote](#remote)
  - [restore](#restore)

<h2 id="version">git version</h2>

git のバージョンを表示。

```
git version
```

<h2 id="init">git init</h2>

リポジトリを新規作成。プロジェクトの開始時に行う。

```
git init
```

<h2 id="pull">git pull</h2>

[プルとは](/EXPLANATION.md#pull)<br>

リモートリポジトリの変更内容をローカルリポジトリに統合する。

```
git pull [マージ元のリモートリポジトリ名] [マージ先のローカルリポジトリ名]
```

<h2 id="push">git push</h2>
ローカルリポジトリの変更内容をリモートリポジトリに統合する。

```
git push  [マージ先のリモートリポジトリ名] [マージ元のローカルリポジトリ名]
```

```
git push origin localbranch:remotebranch
```

<h2 id="add">git add</h2>
ワークスペースに新しく追加/変更/削除したファイルをステージングにする。

```
git add [ステージングするファイル名]
```

[ステージングするファイル名]の部分に[.]を入力するとすべてのファイルをステージングにする

<h2 id="commit">git commit</h2>

メッセージ付きコミット。

```
git commit -m "[コミットメッセージ]"
```

<h2 id="reset">git reset</h2>
ステージングにある全ファイルをワークツリーに戻す

```
git reset HEAD
```

<h2 id="revert">git revert</h2>

直前のコミットを元に戻すコミットを作成する

```
git revert HEAD
```

特定のコミットを元に戻すコミットを作成する

```
git revert [取り消すコミットID]
```

二つ前のコミットなどを取り消せる。<br>
コミット ID は[git log]等で確認できる。

<h2 id="log">git log</h2>
コミット履歴を表示する。

```
git log
```

表示内容

- コミット ID
- 変更者の氏名・メールアドレス(基本的に自分の情報)
- 変更日時
- コミット時に入力したコミットメッセージ

<h2 id="tag">git tag</h2>
コミットにタグを付ける。

```
git tag [tag名]
```

変更履歴の確認時に目印となる。

<h2 id="status">git status</h2>
作業ツリー内の差分ファイルを表示

```
git status
```

- Git の管理対象に含まれていない（新たに追加した）ファイル
- ステージングに追加されたが、まだコミットされていないファイル
- ステージングに追加されていないが、変更されているファイル

<h2 id="diff">git diff</h2>

[ディフとは](/EXPLANATION.md#diff)<br>

作業ファイルをリモートリポジトリのものと比較し差分を表示する。

```
git diff [変更を確認するファイル名またはディレクトリ(省略可)]
```

<h2 id="stash">git stash</h2>

作業ツリーの状態を一時的に退避する。

```
git stash -u
```

退避した作業の一覧を見る。

```
git stash list
```

退避した作業を戻す。

```
git stash apply [stash@{0}]
```

退避した作業を消す。

```
git stash drop [stash@{0}]
```

退避した作業を戻して消す。

```
git stash pop [stash@{0}]
```

退避した作業をすべて消す。

```
git stash clear
```

<h2 id="branch">git branch</h2>

[ブランチとは](/EXPLANATION.md#branch)<br>

ブランチを作成する。

```
git branch [作成するブランチ名]
```

ローカルブランチの確認。

```
git branch
```

リモートブランチの確認。

```
git branch -r
```

ローカルリモート含めてすべてのブランチ一覧を表示

```
git branch -a
```

ローカルのブランチ名変更

```
git branch -m <branch-name> <new-branch-name>
```

ローカルブランチの削除。

```
git branch -d <branch>
```

<h2 id="checkout">git checkout</h2>
作業ブランチを切り替える。

```
git checkout [切り替えるブランチ名]
```

新しいブランチを作成して切り替える。

```
git checkout -b [新しいブランチ名]
```

<h2 id="switch">git switch</h2>

作業ブランチを切り替える。

```
git switch [ブランチ名]
```

ブランチを新規作成して切り替える。

```
git switch -c [ブランチ名]
```

<h2 id="merge">git merge</h2>

[マージとは](/EXPLANATION.md#merge)<br>

現在処理しているブランチに、別のブランチから変更点を取り込む

```
git merge [変更点の取り込み元ブランチ名]
```

<h2 id="remote">git remote</h2>

ローカルに登録済みのリモートリポジトリの情報を削除する。

```
git remote rm <remote-name>
```

<h2 id="restore">git restore</h2>

ファイルの変更を取り消す。

```
git restore <filename>
```

ファイルの変更をすべて取り消す

```
git restore .
```
