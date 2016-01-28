### Verbose checkout

When we checkout a new branch, we do something like this

```bash
$ git checkout -b new-branch
```

Similarly we can use the verbose form of `checkout`, where we explicitly specify the base branch. For example:

```bash
$ git checkout -b new-branch master
```

Is basically the same as the first command, but instead of starting from `HEAD`, we start from the specified branch to determine the commit to point at