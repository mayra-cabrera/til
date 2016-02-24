### Knowing git diff

You probably use `git diff` on a daily basis to show changes between commits. But there are several flags for this command that you might been not aware of like `--word-diff` or `--color-words`

So:

```bash
$ git diff --word-diff 
```

Will show a word diff using a whitespace to delimit changed words

And

```bash
git diff --word-diff --color-words
```

it will display a colored output. Color settings can be changed by `color.ui` and `color.diff` configuration settings

Checkout the [complete documentation](https://git-scm.com/docs/git-diff) for `git diff`command is very resourful