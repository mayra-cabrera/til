## Git Stash

Use this command as your panic button. Imagine uou need to make an emergency in another branch? `git stash` is your friend!  This command will grab all the changes in the working directory and store them away.

One caveat that makes `git stash`slighly less than ideal is that by default it will only bran changes to file already known to Git. This means it will *leave behind* any new or untracked files. :( Luckily, we can solve this with `-u`, that stands for "include untracked":

```bash
$ git stash -u
```
