# linux - install fzf

[junegunn/fzf](https://github.com/junegunn/fzf) is a general-purpose command-line fuzzy finder

## Installation Steps

I want to store this to my `.dotfiles` gnustow management: .dotfiles/submodules/fzf:

```bash
cd .dotfiles
mkdir submodules
cd submodules
git submodule add https://github.com/junegunn/fzf
fzf/install
```

Finished. Restart your shell or reload config file.

```basj
source ~/.bashrc  # bash
source ~/.zshrc   # zsh
```

Use uninstall script to remove fzf.

## ERRORS

### After deleting submodules/fzf folder

```shell
/home/lederich/.fzf.zsh:source:13: datei oder Verzeichnis nicht gefunden: /home/lederich/dev/private/.dotfiles/submodules/fzf/shell/key-bindings.zsh
https://github.com/junegunn/fzf
```

Performed installation steps above --> OK
