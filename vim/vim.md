# VIM

## Install

### 1. Update APT

```shell
sudo apt -y upgrade && sudo apt -y dist-upgrade && sudo apt -y autoremove
```

### 2. Check if Package is available

```shell
sudo apt search vim
```

```shell
sudo apt-cache search vim
```

```shell
sudo apt-cache search vim | grep editor
```

### 3. Install package

```shell
sudo apt-get install vim
```

### 4. Check installed Version

```shell
vim --version
```

### Links

- https://www.cyberciti.biz/faq/howto-install-vim-on-ubuntu-linux/
- https://askubuntu.com/questions/104138/what-features-does-vim-tiny-have
- http://vimdoc.sourceforge.net/htmldoc/options.html#%27compatible%27

## Some commands/settings

`:!ls`	is a call to ls command in the shell == list of your files in the working dir.
`:ls`	is a Vim built-in command, which shows content of buffer list == list of your open filesUse :enew if you 

### open a (new) file in VIM

Do not use `:open`!

* `:edit filename`		if you want to edit a specific file in place of the current one.
* `:new`				if you want to create a new empty buffer in a new horizontal split window.

#### Split view

* `:split filename`		if you want to edit a specific file in a new horizontal split window.
* `:vnew`				if you want to create a new empty buffer in a new vertical split window.
* `:vsplit filename`	if you want to edit a specific file in a new vertical split window.

[how to use vim split screen](https://linuxhint.com/how-to-use-vim-split-screen/)

#### Tab view

* `:tabnew`				if you want to create a new empty tab.
* `:tabedit filename`	if you want to edit a specific file in a new tab

`:set wildcharm=<tab>` for tab completion

### diff

[comparing two files in vim](https://unix.stackexchange.com/questions/1386/comparing-two-files-in-vim)
