## 目次

- [ブランチ](#branch)
- [プルリクエスト(PR)](#pr)
  - [プルリクエストテンプレート作成](#temp)
  - [issue と pullrequest](#issuepr)
- [コンフリクト](#conflict)
- [ディフ](#diff)
- [コミット](#commit)
- [アサイン](#assign)
- [フェッチ](#fetch)
- [マージ](#merge)
- [プル](#pull)
- [イシュー](#issue)
- [リセット](#reset)
- [リモート](#remote)

<h2 id="branch">ブランチ（branch）</h2>

分岐して開発していくための手法。<br>
別々の機能を同時に開発できる。

![ブランチ](/images/branch.png)

<h2 id="conflict">コンフリクト（conflict）</h2>

別々のブランチで、同じファイルの同じ行に異なる変更がなされた場合など、互いに矛盾する行変更を原因とするもの。

下記のような表示が出る。

```
<<<<<<< HEAD
<p>コンフリクト</p>
=======
<p>CONFLICT</p>
>>>>>>> feature
```

手動で必要ないところを削除する。
もしくはエディタ上でどちらかを選択して衝突部分を解決する。

<h2 id="pr">プルリクエスト（pull request(PR)）</h2>
修正した内容で問題ないかレビューをしてもらい、問題なかったら取り込んでくださいとリクエストすること。

![プルリクエスト](/images/pr.png)

<h3 id="temp">pullリクエストの定型文作成</h3>

root 直下か docs フォルダの中に pull_request_template.md を作成し、<br>
マークダウン形式で作成する。<br>
プルリクエストを開くとこんな感じで表示される。

![テンプレート](/images/temp.png)

<h3 id="issuepr">イシューとプルリクエストを関連付ける</h3>

右側の development から issue を選択。<br>
プルリクエストがマージされると issue も同時に close する。

![イシューPR](/images/issuepr.png)

<h2 id="commit">コミット（commit）</h2>
追加・変更したファイルをGitに登録すること。

<h2 id="assign">アサイン（assign）</h2>

issue の画面の右側。<br>
issue にユーザーを割り当てることができる。

![アサイン](/images/assign.png)

<h2 id="diff">ディフ（diff）</h2>
2つのコミットまたは保存された変更間の差異

![ディフ](/images/diff.png)

<h2 id="fetch">フェッチ（fetch）</h2>
変更をコミットせずに、リモートリポジトリからローカルで作業中のブランチに追加する。

<h2 id="merge">マージ（merge）</h2>
1 つのブランチから (同じリポジトリ内で、またはフォークから) 変更を取得し、その変更を別のブランチに適用すること。

<h2 id="pull">プル（pull）</h2>
変更をフェッチしてマージすること。<br>
コンフリクトが発生しないと明確な時には使うと便利。<br>
コンフリクトが起こると面倒なので、そういう場合はfetchとmergeを使う。<br>
pullはfetchとmergeのショートカット。

<h2 id="issue">イシュー（issue）</h2>
リポジトリに関する改善の提案、タスク、または質問のこと。<br>
イシューは下画像のタブから作成できる。

![イシュー](/images/issue.png)

イシューの id (#から始まる数字)をコミットメッセージに添えることで issue とコミットを関連付けることができる。

![イシューID](/images/issuenumber.png)

こんな感じで。

![イシュー解決](/images/issueresolve.png)

#がクリックできるようになり、クリックすると issue が開かれる。<br>
issue に関連したコミットであるということを明示することができて便利。

![イシューマーク](/images/issuemark.png)

<h2 id="reset">リセット（reset）</h2>

```
--hard：「HEADの位置・インデックス・ワーキングツリー」全て
--mixed（or オプション無し）：「HEADの位置・インデックス」
--soft：「HEADの位置」のみ
```

<h2 id="remote">リモート</h2>
他のリポジトリとの接続の作成、内容確認、削除を行うコマンド。

git のリモートリポジトリを削除してローカルのリポジトリを別で接続しようとしたが、すでに削除したリモートリポジトリと接続しているため他のリポジトリに接続はできない。
どうすればよいかというと。

1. git remote コマンドをたたく。　おそらく origin と出る。

![リモート](/images/remote.png)

2. git remote rm [上のコマンドで出た内容ここでは origin]

これで別のリポジトリに切り替えることができます。
