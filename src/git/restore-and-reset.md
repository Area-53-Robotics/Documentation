# Restore and Reset
Eventually, things will go south, and you might need to revert to an older version of your project.

If you want to revert individual files to HEAD (the latest commit on your current branch) you can use:
```sh
git revert myfile.txt # This will permanently delete all of your changes
```
If you want to discard all changes that you've made, you can run:
```sh
git reset --hard # This will permanently delete all of your changes
```