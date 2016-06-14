training-git
============
こちらのトレニング用のガイドでGithubを使って、 [gitflow workflow](http://keijinsonyaban.blogspot.jp/2010/10/successful-git-branching-model.html) の基本のコンセプト（Pull requests, conflictsなど）を簡単に説明させて頂きます。

Setting Up（セットアップ）
----------
Before we can begin with our tutorial, there is a bit of setup involved to help us along the way.
このチュートリアルを始める前に、必要なセットアップがありますので、下記のステップの通りに進めんてください。

#### Fork（フォーク）
Please fork this repository by clicking the `Fork` button on the top right hand side
こちらのリポジトリ（https://github.com/Wizcorp/training_git）を　`Fork`　してください（右の上の `Fork` ボタン）。

#### Clone（クローン）
Once the project has been forked, proceed by cloning the repository
自分のフォークが出来てから、リポジトリを自分のローカルにクローンしてください。（下記のコマンドになります。）

`git clone ssh://git@github.com/YOURNAME/training_git`

#### Add Upstream（Upstreamを追加）
To be able to pull in changes from the blessed repo we need to add it as an upstream
メーンリポジトリ（＝Upstream）から最新コードのPullが出来るように、Upstreamはどのリポジトリかを指定する必要です。（下記のコマンドになります。）

`git remote add upstream ssh://git@github.com/Wizcorp/training_git.git`


First Pull Request（初めてのPull Request）
------------------
Here we will take you through the pull request process and have you perform your first pull request. What you will be
doing for your first fix is to update the title of this README file `training-git` to `Training - GIT`. Please follow
the following instruction set to get to the PR review stages:
こちらのセクションでPull Requestのフローを説明すると、自分で初のPull Requestの作成するために、案内します。
初のPRとして、READMEファイルのタイトルを`training-git`から`Training - GIT`に変更しましょう。
次のステップの通りにすすんでみてください。

#### Branch（ブランチ）
Create a branch dedicated to your fix, branching it from the master branch
今回の修正用のブランチをMasterブランチから作成しましょう。（下記のコマンドになります。）

`git branch feature/titleFix master`

#### Checkout（チックアウト）
Now that the branch has been created, you will need to check it out to make changes
先のコマンドでブランチが作られています。これから編集するためにそのブランチからチックアウトします。（下記のコマンドになります。）

`git checkout feature/titleFix`

#### Modify（編集）
From this point you can begin making changes, please alter the `README.md` file title to `Training - GIT`
チックアウトが終わったので、これから編集が出来ます。`README.md`のタイトルを `Training - GIT` にしてください。

#### Status（ステータス）
Before we begin committing our work, let's take a quick look at the status of the project
編集した内容をコミットする前に、プロジェクトのステータスを確認しましょう。（下記のコマンドになります。）

`git status`

#### Stage（ステージ）
We now have to commit our work, so firstly we need to stage the changes
これから編集した内容をコミットしますが、その前に、コミットしたい内容をステージをしましょう。（下記のコマンドになります。）

`git add README.md`

#### Commit（コミット）
And then we commit it
ステージされた内容をコミットしましょう。（下記のコマンドになります。）

`git commit -m "YOUR COMMIT MESSAGE HERE"`

#### Pull（プル）
At this point we should usually pull in any changes that may have occurred in the meantime on the master branch
ここまで進むとUpstreamのMasterブランチで最終のPullから他の変更が行ったかも知れないので、Pullしましょう。（下記のコマンドになります。）

`git pull upstream master`

#### Push（プッシュ）
Then we push the branch up to our fork creating the branch on the remote
それからこのブランチを自分のフォークにプッシュしましょう。そうすると、リモートでそのブランチが追加されます。（下記のコマンドになります。）

`git push origin feature/titleFix`

#### Pull Request（プル　リグエスト）
Lastly we initiate a pull request to the origin blessed repository using the `Pull Request` button from your fork
最終的にUpstreamにPull Requestを作りましょう。
自分のフォーク（https://github.com/YOURNAME/training_git）から　`Pull Request`　のボタンを押してください。


First Conflict　（初めてのコンフリクト）
--------------
Here we will help you face and resolve a git conflict by trying to simulate the situation. We have the following
sentence `She sells sea-shells on the sea-shore.`. What we will do is modify this sentence to contain `by the seashore`
as opposed to `on the sea-shore`.

このセクションでgitでのコンフリクトを解決方法を試しましょう。
あるブランチに`She sells sea-shells on the sea-shore.`の文章が入っています。その文章の`on the sea-shore`を`by the seashore`に変更しましょう。

#### Branch（ブランチ）

その文章が置いてあるブランチに移動しましょう。（下記のコマンドになります。）

`git branch feature/sentenceFix master`

#### Checkout（チックアウト）
そのブランチをチックアウトしましょう。（下記のコマンドになります。）

`git checkout feature/sentenceFix`

#### Modify
`She sells sea-shells on the sea-shore.`の文章が入っています。その文章の`on the sea-shore`を`by the seashore`に変更しましょう。

#### Status（ステータス）
（下記のコマンドになります。）

`git status`

#### Stage（ステージ）
（下記のコマンドになります。）

`git add README.md`

#### Commit（コミット）
（下記のコマンドになります。）

`git commit -m "YOUR COMMIT MESSAGE HERE"`

#### Pull（プル）
Here to simulate the conflict resolution we will pull from a different upstream branch `conflict`
コンフリクトを起こすために、Upstreamの別のブランチからプルしましょう。

`git pull upstream conflict`

#### Conflict Resolution　（コンフリクトの解決）
You should now be faced with a conflict. You can quickly check which files contain a conflict by taking a look at this
project `status`. When you open the file you should notice a section wrapped by `<<<<<`, `=====` and`>>>>>`. The goal is
to remove one or merge then together into one. Once you have resolved the conflict, removed the encapsulation text
`<<<<<`, `=====` and`>>>>>`.
現時点で、コンフリクトが発生したはずです。どのファイルにコンフリクトがおきているかを確認するために、プロジェクトの `status`の確認しましょう。
そのファイルを開くと`<<<<<`, `=====` と`>>>>>`のセクションの確認が出来ます。目的は一つを外すか両方をマージするかです。その解決してから`<<<<<`, `=====` と`>>>>>`を外してください。

#### Stage（ステージ）

#### Commit（コミット）

#### Push（プッシュ）
（下記のコマンドになります。）

`git push origin feature/sentenceFix`

#### Pull Request（プル　リクエスト）
