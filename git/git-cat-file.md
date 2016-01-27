### Git cat-file

When we add objects to some git repository, what we are actually adding are "blobs". Blog stores **only the contents** of the files, it doesn't store the name. 

Git uses blocks to track files. If we want to see this we can ask Git to show the content of our stored object using `cat-file` command

```bash
$ git cat-file -p 08d16a7c
kitties kitties kitties
```

We only need to provide the first eight or so characters, we don't need to provide the whole sha