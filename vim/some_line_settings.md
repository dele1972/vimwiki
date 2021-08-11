":set wrap						" To wrap lines visually, i.e. the line is still one line of text, but Vim displays it on multiple lines.
:set nowrap						" To display long lines as just one line (i.e. you have to scroll horizontally to see the entire line)


" turn absolute line numbers on
:set number
:set nu

" turn absolute line numbers off
:set nonumber
:set nonu

" toggle absolute line numbers
:set number!
:set nu!



" turn relative line numbers on
:set relativenumber
:set rnu

" turn relative line numbers off
:set norelativenumber
:set nornu

" toggle relative line numbers
:set relativenumber!
:set rnu!


" turn hybrid line numbers on
:set number relativenumber
:set nu rnu

" turn hybrid line numbers off
:set nonumber norelativenumber
:set nonu nornu

" toggle hybrid line numbers
:set number! relativenumber!
:set nu! rnu!
