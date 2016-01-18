## Searching the logs by commit message

Occasionally we'll need to go deeper into the history looking for changes related to specific part of our application. For these cases we can use `git log --grep`, as it follows:

```bash
git log --grep -E -i 'ticket(s)'
```

This searched the commit logs for all commits with any form of "ticket" or "tickets" in the commit message. Breaking down the specific options, we have:

* `--grep`: Search the log for specified string or pattern
* `-E`: Use "extended regular expressions" when interpreting the search pattern
* `-i`: Search case insentively

But this is perhaps more than we want to have to remember **and type**, so again `git config alias` to the rescue:

```bash
$ git config --global alias.glog `log -E -i --grep`
```

With that in place, we can do the same as above just by typing the following:

```bash
git glog 'ticket(s)'
```

But what about if we want to search for changes related to a particular strings in our code base. Luckily `git log`supports another flag: `-S`. For instance, we can run the following to search for any time we added or removed a call to `with_active_tickets`method:

```bash
$ git log -S with_active_tickets
```

Also in some cases, we may want to see the changes to a single file to understand that file's unique history. And of course we can do that with:

```bash
$ git log --oneline -- Gemfile
```


So finally once we've found a commit of interested, we can use the `git show` command to display the commit info and a diff of the changes the commit introduced:

```bash
$ git show 770b1ab6
```


