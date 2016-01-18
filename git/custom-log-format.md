Custom Log Format
==

Say we want to include the date and author, in addition to the commit hash and message. We can use the following:

```bash
$ git log --pretty=format: '%h - %an [%ar] %s`
```

Let's break down:

* `%h`: Abbreviated commit hash
* `%an`: Author name
* `%ar`: Commit authored on friendly date
* `%s`: Commit subject 

In addition, we can pimp this up by adding a little color. Colors are specified with `%C(<color-name>)`, with `%C(reset)` resetting the color. So with the following command, we color the commit hash yellow and the date green:

```bash
$ git log --pretty=format:'%C(yellow)%h%C(reset) - %an [%C(green)%ar%C(reset)] %s'
```
