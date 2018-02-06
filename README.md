# justyre.github.io

This is a [blogging website](http://justyre.github.io) designed using Pelican, Github Pages, Python 3 and Jupyter Notebook. The local environment is M$ Windows 10 with an office network connection, which is behind a firewall and has few opened net ports.

## Updating the Blog

Note that there are certain **CAVEATS** and messing up the order of steps below may cause fatal data loss.

1. (Not Essential) If any other file update is desired other than the Github Page-generating mission, use the `dev` branch instead of `master` (where the blog is hosted). Suppose that we made some modifications and want to update `.gitignore` and `README.md`. Run the following in Git bash:

   1. If we have NOT created the branch `dev` before, run:
   ```
   git checkout -b dev
   ```

   2. If we have the branch `dev` already, run:
   ```
   git checkout dev
   ```

   After the above switch of branches, run:
   ```
   git add .gitignore README.md
   git commit -m 'modified branch: dev. J20180203'
   git push origin dev 
   ```

2. If desired, change the `THEME` parameter in `publishconf.py`.

3. Run in Git bash consecutively: (surely we already have the branch `master`)
   ```
   pelican content -s publishconf.py
   ghp-import output -b master
   git push origin master
   ```

4. Now visit `username.github.io`. *Estamos*!

## Tech Logs

**Justyre 20180203:**

When following the steps by courtesy of [this post on dataquest.io](https://www.dataquest.io/blog/how-to-setup-a-data-science-blog/), specifically at the stage of deploying to Github Pages, when I ran:

    git push origin master

I encountered the same problem as described [here](https://stackoverflow.com/questions/15589682/ssh-connect-to-host-github-com-port-22-connection-timed-out), where I carried out the procedures in @Vihari Piratla's answer to fix it:

First, run in Git Bash:

    ssh -T git@github.com
    
this should timeout. If that's the case, use *http protocol* instead of *ssh* this way. Just change your url in the config file to http, by running:
```
git config --local -e
```
then change the entry of (*username* replaced as *justyre* and *repo* replaced as *justyre.github.io* in my case)

    url = git@github.com:username/repo.git
to

    url = https://github.com/username/repo.git
