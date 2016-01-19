## Displaying alias information

Sometimes, or well most of the times, git has commands that are a bit much to remember. Luckily for this, we can use Git's configuration system to save it away asn alias. For example: 

```bash
$ git log --oneline --decorate --graph --all''
```

This creates an alias called `sla` that can be used in place of the more verbose command 

And if you ever want to remember what the alias is about you can use `git help <alias>`

```bash
$ git help sla
`git sla' is aliased to `log --oneline --decorate --graph --all'
```
