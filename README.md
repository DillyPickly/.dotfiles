# .dotfiles
My Linux Configuration Files

## Replicating this setup on a new machine

### Set up repo 
``` bash
  git clone --bare https://github.com/DillyPickly/.dotfiles.git $HOME/.dotfiles
  alias config='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'
  config config --local status.showUntrackedFiles no
```

### Add dotfiles
``` bash
  config checkout 
```
  
## Installing Packages
``` bash
	xargs sudo dnf install -y <.pkglist/dnf.txt
```
with the dnf packages are in the `dnf.txt` file

## To install fonts and change terminal settings
https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k
