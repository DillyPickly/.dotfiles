# .dotfiles
My Linux Configuration Files

### Replicating this setup on a new machine


``` bash
  git clone --bare https://github.com/DillyPickly/.dotfiles.git $HOME/.dotfiles
```
Using `--bare` so as to not get the working tree and revision history


``` bash 
  alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
```
This alias is how I manage the dotfiles each machine

``` bash
  config config --local status.showUntrackedFiles no
```
Set the status so that untracked files do not give messages when calling something like `config status`


``` bash
  config checkout 
```
This will try to write the files from .dotfiles to the home directory and will fail if there are config files currently in the home directly of the same name. Simply delete those configuration files if you dont want them and rerun `config checkout`
  
  
  ### To update my dotfiles
  
  ``` bash
  config status
  config add .vimrc
  config commit -m "Add vimrc"
  config add .bashrc
  config commit -m "Add bashrc"
  config push
  ```
  

Credit to:
https://news.ycombinator.com/item?id=11070797
https://www.atlassian.com/git/tutorials/dotfiles
