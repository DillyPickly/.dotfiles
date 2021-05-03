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
  
  
## Installing Packages
``` bash
	xargs sudo dnf install -y <dnf.txt
```
with the dnf packages are in the `dnf.txt` file

## To install fonts and change terminal settings
https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k
