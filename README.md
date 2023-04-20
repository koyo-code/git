# Git Document

[git 練習用](/TEST.md)<br>

[分かったこと適当に](/STUDY.md)<br>

## 目次

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

<h2 id="init">git init</h2>

リポジトリを新規作成。プロジェクトの開始時に行う。

```
git init
```

<h2 id="pull">git pull</h2>

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
直前のコミットを取消する。

```
git reset
```

<h2 id="revert">git revert</h2>
特定のコミットを取消する。

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
作業ファイルをリモートリポジトリのものと比較し差分を表示する。

```
git diff [変更を確認するファイル名またはディレクトリ(省略可)]
```

<h2 id="stash">git stash</h2>
作業ツリーの状態を一時的に保存する。

```
git stash [実行コマンド]
```

| 実行コマンド | save                   | list                                   | apply                                            | drop                               |
| ------------ | ---------------------- | -------------------------------------- | ------------------------------------------------ | ---------------------------------- |
| 用途         | 作業ツリーの状態を保存 | 保存されたバックアップデータを一覧表示 | 保存されたバックアップデータを使用する環境に戻す | 保存されたバックアップデータを削除 |

<h2 id="branch">git branch</h2>

[ブランチについて](/EXPLANATION.md#branch)

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
現在処理しているブランチに、別のブランチから変更点を取り込む

```
 git merge [変更点の取り込み元ブランチ名]
```
