### Different name for remote

Normally when you're working on a functionality you are in your own branch (otherwise shame on you!), when is time to push our changes to github, you probably do something like this:

```bash
$ git push origin my-awesome-branch
```

And a remote branch called `my-awesome-branch`will be created. But what about if I want to call my remote branch different? Maybe because the project requires so or for some other reason, well as you can imagine there's a command for that:

```bash
git push -u origin my-awesome-branch:some-other-name
```

The former command will create a branch called `some-other-name`that will be the tracking branch for our local branch :) 

