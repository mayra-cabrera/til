## Changes for specific part

In git you can retrieve changes for an specific part of your file with the following command:


```bash
$ git log -L 3,10:app/controllers/users_controller.rb
```

That will display all commits that have changed `users_controller.rb` within lines 3 to 10, you can even say how many commits do you want with:


```bash
$ git log -L 3,10:app/controllers/users_controller.rb -2
```

In the former only two commits will appear. Amazing!

