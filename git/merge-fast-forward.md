### Merge fast-forward

You probably have use `git merge` this will merge a branch into the other one, but it will create a commit indicating the merging, and thats ok ..sometimes. Sometimes though that polutes git history and for that you can either rebase or you use `git merge branch-name --ff-only` command, this will ensure a fast forward merge (duh), and that means no git merge commit :) 

Of course if you have branch that is really different from the branch you want to merge, this is going to be harder to do, thats why you should always break up your changes into small chunks, that way by splitting these changes up, we made our branch easy to merge and also easy to review and give meaningful feedback
