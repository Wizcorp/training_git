Training - GIT
============
This guide is written around the [gitflow workflow](http://nvie.com/posts/a-successful-git-branching-model/) using
GitHub and will cover some basic training topics (Pull requests, conflicts etc).


Setting Up
----------
Before we can begin with our tutorial, there is a bit of setup involved to help us along the way.

#### Fork
Please fork this repository by clicking the `Fork` button on the top right hand side

#### Clone
Once the project has been forked, proceed by cloning the repository

`git clone ssh://git@github.com/YOURNAME/training_git`

#### Add Upstream
To be able to pull in changes from the blessed repo we need to add it as an upstream

`git remote add upstream ssh://git@github.com/Wizcorp/training_git.git`


First Pull Request
------------------
Here we will take you through the pull request process and have you perform your first pull request. What you will be
doing for your first fix is to update the title of this README file `training-git` to `Training - GIT`. Please follow
the following instruction set to get to the PR review stages:

#### Branch
Create a branch dedicated to your fix, branching it from the master branch

`git branch feature/titleFix master`

#### Checkout
Now that the branch has been created, you will need to check it out to make changes

`git checkout feature/titleFix`

#### Modify
From this point you can begin making changes, please alter the `README.md` file title to `Training - GIT`

#### Status
Before we begin committing our work, let's take a quick look at the status of the project

`git status`

#### Stage
We now have to commit our work, so firstly we need to stage the changes

`git add README.md`

#### Commit
And then we commit it

`git commit -m "YOUR COMMIT MESSAGE HERE"`

#### Pull
At this point we should usually pull in any changes that may have occurred in the meantime on the master branch

`git pull upstream master`

#### Push
Then we push the branch up to our fork creating the branch on the remote

`git push origin feature/titleFix`

#### Pull Request
Lastly we initiate a pull request to the origin blessed repository using the `Pull Request` button from your fork


First Conflict
--------------
Here we will help you face and resolve a git conflict by trying to simulate the situation. We have the following
sentence `She sells sea-shells by the seashore.`. What we will do is modify this sentence to contain `by the seashore`
as opposed to `on the sea-shore`.

#### Branch

`git branch feature/sentenceFix master`

#### Checkout

`git checkout feature/sentenceFix`

#### Modify
Modify the above sentence as written there.

#### Status

`git status`

#### Stage

`git add README.md`

#### Commit

`git commit -m "YOUR COMMIT MESSAGE HERE"`

#### Pull
Here to simulate the conflict resolution we will pull from a different upstream branch `conflict`

`git pull upstream conflict`

#### Conflict Resolution
You should now be faced with a conflict. You can quickly check which files contain a conflict by taking a look at this
project `status`. When you open the file you should notice a section wrapped by `<<<<<`, `=====` and`>>>>>`. The goal is
to remove one or merge then together into one. Once you have resolved the conflict, removed the encapsulation text
`<<<<<`, `=====` and`>>>>>`.

#### Stage

#### Commit

#### Push

`git push origin feature/sentenceFix`

#### Pull Request
