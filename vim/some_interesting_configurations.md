# some interesting Vim configs

## Sebastian Daschner's [.vimrc](https://github.com/sdaschner/dotfiles/blob/master/.vimrc)


### opens a new empty buffer

```vim
" opens a new empty buffer
nmap <leader>t :enew<CR>
```

### Disable Arrow Keys

```vim
inoremap <Up> <NOP>
inoremap <Down> <NOP>
inoremap <Left> <NOP>
inoremap <Right> <NOP>
noremap <Up> <NOP>
noremap <Down> <NOP>
```

### shows all open buffers and their status

```vim
" shows all open buffers and their status
nmap <leader>bl :ls<CR>
```

### toggles word wrap

```vim
" toggles word wrap
nmap <C-w> :set wrap! linebreak<CR>
```

### opens the last buffer

```vim
" opens the last buffer
nnoremap <leader><leader> <C-^>
```

### file operations

```vim
" file operations
nmap <C-s> :w<CR>
nmap <C-q> :q<CR>
```

### system clipboard

```vim
" system clipboard
vmap <leader>y "+y
vmap <leader>d "+d
nmap <leader>y "+yy
nmap <leader>p "+p
nmap <leader>P "+P
vmap <leader>p "+p
vmap <leader>P "+P

nmap <leader>d <C-d>
nmap <leader>u <C-u>
vmap <leader>d <C-d>
vmap <leader>u <C-u>
```

### removes search highlighting

```vim
" removes search highlighting
nnoremap <silent> <C-l> :nohl<CR><C-l>
```

### AsciiDoc preview

```vim
" AsciiDoc preview
nmap <leader>v :!asciidoc-view %<CR><CR>
```

