# Remote Branches
One of the most useful features of git is the ability to have remote branches. This is usually a git repository hosted on github. To link your local repository to your remote one, you need it's url. Github provides HTTPS and SSH as ways to do this. We recomend SSH, as the authentication is easier to set up. We won't cover how to do that here, but here is [github's documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh) on how to set up authentication via SSH keys. Alternativly, repositories cloned through VSCode should have this automatically set up for you.

Once you have the url you can add the remote repo using:
```sh
git remote add origin git@github.com:User/Repository.git # SSH
```
> Note: This creates a remote repo called origin. Origin is the standard name for remote repos. While it is possible to have multiple remotes, it is highly unlikely.

You can push and pull to remote branches like you would any other branch. 
```sh
git pull origin master # Pulls from a branch on origin called master
git push origin master 
```