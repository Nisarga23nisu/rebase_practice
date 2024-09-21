# rebase_practice

# git clone https://github.com/Nisarga23nisu/rebase_practice.git
Cloning into 'rebase_practice'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.

# cd rebase_practice/
# ubuntu@ip-172-31-6-116:~/rebase_practice$ git branch
* master
# git branch feature1
# git branch
  feature1
* master
# git checkout feature1 
Switched to branch 'feature1'
# git branch
* feature1
  master
# ubuntu@ip-172-31-6-116:~/rebase_practice$ vi f1
# git add f1 
# git commit -m "added file f1"
[feature1 a2cedad] added file f1
 Committer: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 f1
# git log
commit a2cedad70052cfe1a2659a3ed472f72a1dddc169 (HEAD -> feature1)
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:32:29 2024 +0000

    added file f1

commit 85280a2fc0af2fd26ee07dd9997b876cdfbb171b (origin/master, origin/HEAD, master)
Author: Nisarga23nisu <156158786+Nisarga23nisu@users.noreply.github.com>
Date:   Sat Sep 21 12:58:55 2024 +0530

    Initial commit
# vi f1
# git add f1 
# git commit -m "modified file f1"
[feature1 15fbd3f] modified file f1
 Committer: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
# git log
commit 15fbd3ffedbb421378f6db964e17c2eac33ccaea (HEAD -> feature1)
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:33:51 2024 +0000

    modified file f1

commit a2cedad70052cfe1a2659a3ed472f72a1dddc169
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:32:29 2024 +0000

    added file f1

commit 85280a2fc0af2fd26ee07dd9997b876cdfbb171b (origin/master, origin/HEAD, master)
Author: Nisarga23nisu <156158786+Nisarga23nisu@users.noreply.github.com>
Date:   Sat Sep 21 12:58:55 2024 +0530


# git checkout master
Switched to branch 'master'
Your branch is up to date with 'origin/master'.
ubuntu@ip-172-31-6-116:~/rebase_practice$ git branch
  feature1
* master
# vi f2
# git add f2
# git commit -m "added file f2"
[master 170b635] added file f2
 Committer: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 f2
# git log
commit 170b63582c3cf097470ad78b1b0e40f62821ca0c (HEAD -> master)
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:35:50 2024 +0000

    added file f2

commit 85280a2fc0af2fd26ee07dd9997b876cdfbb171b (origin/master, origin/HEAD)
Author: Nisarga23nisu <156158786+Nisarga23nisu@users.noreply.github.com>
Date:   Sat Sep 21 12:58:55 2024 +0530

    Initial commit
# vi f2
# git add f2
# git commit -m "modified file f2"
[master 5ea7111] modified file f2
 Committer: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

commit 5ea71115444d597dc5eabd1a35d7edc471d89c8e (HEAD -> master)
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:36:43 2024 +0000

    modified file f2

commit 170b63582c3cf097470ad78b1b0e40f62821ca0c
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:35:50 2024 +0000

    added file f2

commit 85280a2fc0af2fd26ee07dd9997b876cdfbb171b (origin/master, origin/HEAD)
Author: Nisarga23nisu <156158786+Nisarga23nisu@users.noreply.github.com>
Date:   Sat Sep 21 12:58:55 2024 +0530

    Initial commit

# git rebase feature1 master
Successfully rebased and updated refs/heads/master.
# git log
commit a4ae11eadf9dfe488d83b7220a4c3aed6b570231 (HEAD -> master)
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:36:43 2024 +0000

    modified file f2

commit 5d635cf02decda2834b6e2c4833f3a8f7ea7c0ad
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:35:50 2024 +0000

    added file f2

commit 15fbd3ffedbb421378f6db964e17c2eac33ccaea (feature1)
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:33:51 2024 +0000

    modified file f1

commit a2cedad70052cfe1a2659a3ed472f72a1dddc169
Author: Ubuntu <ubuntu@ip-172-31-6-116.ap-south-1.compute.internal>
Date:   Sat Sep 21 07:32:29 2024 +0000

    added file f1

commit 85280a2fc0af2fd26ee07dd9997b876cdfbb171b (origin/master, origin/HEAD)
Author: Nisarga23nisu <156158786+Nisarga23nisu@users.noreply.github.com>
Date:   Sat Sep 21 12:58:55 2024 +0530

    Initial commit
