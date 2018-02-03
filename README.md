# justyre.github.io

This is a [blogging website](http://justyre.github.io) designed using Pelican, Github Pages, Python 3 and Jupyter Notebook. The local environment is M$ Windows 10 with an office network connection, which is behind a firewall and has few opened net ports.

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
