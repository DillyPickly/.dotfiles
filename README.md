# .dotfiles
My Linux Configuration Files

### Replicating this setup on a new machine

```bash
  git clone --bare <git-repo-url> $HOME/.dotfiles
  cp ~/myconf-tmp/.gitmodules ~  # If you use Git submodules
  rm -r ~/myconf-tmp/
  alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
  
```




Credit to:
https://news.ycombinator.com/item?id=11070797
https://www.atlassian.com/git/tutorials/dotfiles
