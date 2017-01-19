training-git
============
こちらのトレニング用のガイドでGithubを使って、 [gitflow workflow](http://keijinsonyaban.blogspot.jp/2010/10/successful-git-branching-model.html) の基本のコンセプト（Pull requests, conflictsなど）を簡単に説明させて頂きます。

Setting Up（セットアップ）
----------
このチュートリアルを始める前に、必要なセットアップがありますので、下記のステップの通りに進めんてください。

#### Fork（フォーク）
こちらのリポジトリ（https://github.com/Wizcorp/training_git）を　`Fork`　してください（右の上の `Fork` ボタン）。

#### Clone（クローン）
自分のフォークが出来てから、リポジトリを自分のローカルにクローンしてください。（下記のコマンドになります。）

`git clone ssh://git@github.com/アカウント名/training_git`

#### Add Upstream（Upstreamを追加）
メーンリポジトリ（＝Upstream）から最新コードのPullが出来るように、Upstreamはどのリポジトリかを指定する必要です。（下記のコマンドになります。）

`git remote add upstream ssh://git@github.com/Wizcorp/training_git.git`


First Pull Request（初めてのPull Request）
------------------
こちらのセクションでPull Requestのフローを説明すると、自分で初のPull Requestの作成するために、案内します。
初のPRとして、READMEファイルのタイトルを`training-git`から`Training - GIT`に変更しましょう。
次のステップの通りにすすんでみてください。

#### Branch（ブランチ）
今回の修正用のブランチをMasterブランチから作成しましょう。（下記のコマンドになります。）

`git branch feature/titleFix master`

#### Checkout（チックアウト）
先のコマンドでブランチが作られています。これから編集するためにそのブランチからチックアウトします。（下記のコマンドになります。）

`git checkout feature/titleFix`

#### Modify（編集）
チックアウトが終わったので、これから編集が出来ます。`README.md`のタイトルを `Training - GIT` にしてください。

#### Status（ステータス）
編集した内容をコミットする前に、プロジェクトのステータスを確認しましょう。（下記のコマンドになります。）

`git status`

#### Stage（ステージ）
これから編集した内容をコミットしますが、その前に、コミットしたい内容をステージをしましょう。（下記のコマンドになります。）

`git add README.md`

#### Commit（コミット）
ステージされた内容をコミットしましょう。（下記のコマンドになります。）

`git commit -m "コミットメッセージをここに書いてください"`

#### Pull（プル）
ここまで進むとUpstreamのMasterブランチで最終のPullから他の変更が行ったかも知れないので、Pullしましょう。（下記のコマンドになります。）

`git pull upstream master`

#### Push（プッシュ）
それからこのブランチを自分のフォークにプッシュしましょう。そうすると、リモートでそのブランチが追加されます。（下記のコマンドになります。）

`git push origin feature/titleFix`

#### Pull Request（プル　リグエスト）
最終的にUpstreamにPull Requestを作りましょう。
自分のフォーク（https://github.com/アカウント名/training_git）から　`Pull Request`　のボタンを押してください。


First Conflict　（初めてのコンフリクト）
--------------
このセクションでgitでのコンフリクトを解決方法を試しましょう。
あるブランチに`She sells sea-shells on the sea-shore.`の文章が入っています。その文章の`on the sea-shore`を`by the seashore`に変更しましょう。

#### Branch（ブランチ）

その文章が置いてあるブランチに移動しましょう。（下記のコマンドになります。）

`git branch feature/sentenceFix master`

#### Checkout（チックアウト）
そのブランチをチックアウトしましょう。（下記のコマンドになります。）

`git checkout feature/sentenceFix`

#### Modify（編集）
`She sells sea-shells by the sea-shore.`の文章が入っています。その文章の`on the sea-shore`を`by the seashore`に変更しましょう。

#### Status（ステータス）
（下記のコマンドになります。）

`git status`

#### Stage（ステージ）
（下記のコマンドになります。）

`git add README.md`

#### Commit（コミット）
（下記のコマンドになります。）

`git commit -m "コミットメッセージをここに書いてください"`

#### Pull（プル）
コンフリクトを起こすために、Upstreamの別のブランチからプルしましょう。

`git pull upstream conflict`

#### Conflict Resolution　（コンフリクトの解決）
現時点で、コンフリクトが発生したはずです。どのファイルにコンフリクトがおきているかを確認するために、プロジェクトの `status`の確認しましょう。
そのファイルを開くと`<<<<<`, `=====` と`>>>>>`のセクションの確認が出来ます。目的は一つを外すか両方をマージするかです。その解決してから`<<<<<`, `=====` と`>>>>>`を外してください。

#### Stage（ステージ）

#### Commit（コミット）

#### Push（プッシュ）
（下記のコマンドになります。）

`git push origin feature/sentenceFix`

#### Pull Request（プル　リクエスト）
