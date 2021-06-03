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
with the dnf packages in  `dnf.txt` 

## Installing Manual Packages
``` bash
./.pkglist/manual.sh
```

## To finish installation 
 - Log out
 - Change terminal font to MesloLGS
