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

I use zsh-autosuggestions and zsh-syntax-highlighting. Those need to be downloaded [here](https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh) and [here](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md#oh-my-zsh)

If you get broken characters in the terminal fromt the zsh fonts be sure to change the font in the terminal emulator. For example in default gnome go to the xterm setting and change the font. Many of the themes need powerline fonts which can be found [here](https://github.com/powerline/fonts#installation)

### I currently use gnome setup
simply install the `gnome` and `gnome-tweaks` packages [More Info](https://wiki.archlinux.org/index.php/GNOME#Installation). Then enable the `systemctl enable gdm.service` to start gnome at boot.

THe most important extensions that I use are the dash to dock extension and user themes extension for a desktop dock and theming. I also use few others for conveniece like caffeine

###


  

### Other Resources:

- https://news.ycombinator.com/item?id=11070797
- https://www.atlassian.com/git/tutorials/dotfiles
- http://www.saintsjd.com/2011/01/what-is-a-bare-git-repository/
