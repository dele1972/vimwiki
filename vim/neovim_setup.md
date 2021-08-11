neovim


## Getting started with Neovim

https://www.dwarmstrong.org/neovim/

sudo apt install neovim
mkdir ~/.config/nvim
touch ~/.config/nvim/init.vim
nvim ~/.config/nvim/init.vim

set nocompatible            " disable compatibility to old-time vi
set showmatch               " show matching brackets.
set ignorecase              " case insensitive matching
set mouse=v                 " middle-click paste with mouse
set hlsearch                " highlight search results
set tabstop=4               " number of columns occupied by a tab character
set softtabstop=4           " see multiple spaces as tabstops so <BS> does the right thing
set expandtab               " converts tabs to white space
set shiftwidth=4            " width for autoindents
set autoindent              " indent a new line the same amount as the line just typed
set number                  " add line numbers
set wildmode=longest,list   " get bash-like tab completions
set cc=80                   " set an 80 column border for good coding style
filetype plugin indent on   " allows auto-indenting depending on file type
syntax on                   " syntax highlighting




## Setting Up Neovim for Web Development in 2020

https://medium.com/better-programming/setting-up-neovim-for-web-development-in-2020-d800de3efacd

curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim


### error: nvim starts with error - unknown function: plug#begin
put the suggested snippet to the top of ~/.config/nvim/init.vim
https://github.com/junegunn/vim-plug/issues/245#issuecomment-388178498


## copy to clipboard


### install xclip

https://stackoverflow.com/a/55662625

$ sudo apt-get install xclip


### set up neovim config

https://vi.stackexchange.com/a/15213

let g:clipboard = {
  \   'name': 'xclip-xfce4-clipman',
  \   'copy': {
  \      '+': 'xclip -selection clipboard',
  \      '*': 'xclip -selection clipboard',
  \    },
  \   'paste': {
  \      '+': 'xclip -selection clipboard -o',
  \      '*': 'xclip -selection clipboard -o',
  \   },
  \   'cache_enabled': 1,
  \ }


### copy and paste

https://stackoverflow.com/questions/3961859/how-to-copy-to-clipboard-in-vim

"*yy			To copy the current line, in command mode
"*yG			To copy the whole file/buffer, in command mode, first go to the beginning via gg


https://superuser.com/questions/227385/how-do-i-select-all-text-in-vi-vim
https://advancedweb.hu/working-with-the-system-clipboard-in-vim/
https://stackoverflow.com/questions/7942653/vim-y-and-trailing-characters/7943665#7943665




