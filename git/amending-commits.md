## Amending Commits

Must of you know about `git commit --amend` command, yup the command that come in handy when we find ourselves in a situation where we've made committed some changes, only to realize we forgot to add a file that was a part of the change!

But there's another flag that is really helpful in this command and that is `--no-edit`, so:

```bash
$ git commit --amend --no-edit
```

This will take the currently-staged changes and incorporate them into the previous commit, reusing the existing commit message. 