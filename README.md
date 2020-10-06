# .dotfiles
My Linux Configuration Files

### Replicating this setup on a new machine


``` bash
  git clone --bare https://github.com/DillyPickly/.dotfiles.git $HOME/.dotfiles
```
Using [`--bare`](https://git-scm.com/docs/git-clone#Documentation/git-clone.txt---bare) 


``` bash 
  alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
```
This alias is how I manage the dotfiles each machine. To make sure that this alias is permanent I have added the above line to my `.zshrc`

``` bash
  config config --local status.showUntrackedFiles no
```
Set the status so that untracked files do not give messages when calling something like `config status`


``` bash
  config checkout 
```
This will try to write the files from .dotfiles to the home directory and will fail if there are config files currently in the home directly of the same name. Simply delete those configuration files if you dont want them and rerun `config checkout`
  
  
### To update my dotfiles locally and push

``` bash
  config status
  config add .zshrc
  config commit -m "Add bashrc"
  config push
```
  
 
### ZSH and Oh My Zsh
The configuration of ZSH is done by the `.zshrc` file. To get your set up working like mine. Follow the instrucitons to install ZSH and Oh My Zsh [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#zsh) and [here](https://github.com/ohmyzsh/ohmyzsh#basic-installation). Then, replace the default `.zshrc` file with the one in this repo (when checking out)

I use zsh-autosuggestions and zsh-syntax-highlighting. Those need to be downloaded [here](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh) and [here](https://github.com/zsh-users/zsh-syntax-highlighting.git)

  

### Other Resources:

- https://news.ycombinator.com/item?id=11070797
- https://www.atlassian.com/git/tutorials/dotfiles
- http://www.saintsjd.com/2011/01/what-is-a-bare-git-repository/
