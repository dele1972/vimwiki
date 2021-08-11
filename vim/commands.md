ve	Select from cursor to end of the word	(https://superuser.com/questions/463334/vim-how-to-select-a-line-up-to-the-cursor-including-the-char-under-the-cursor)
v$	Select from cursor to end of the line

	then
	x	delete
	go to next occurance
	.	redo the selection and delete action!

## coppy/cut and paste (https://stackoverflow.com/a/1061951)

### copy

yi'	yank to next '
vi) visual mode selection to next )
vi} visual mode selection to next }
vi' visual mode selection to next '

### cut



### paste

p



## vi commands (https://www.cs.colostate.edu/helpdocs/vi.html)

	x - delete
	G - Cursor in letzte Zeile
	o - Neue Zeile nach Cursor einfügen


## Commenting out a block of code with Vim

https://eli.thegreenplace.net/2010/08/25/commenting-out-a-block-of-code-with-vim

1. Move to the first column in the first line you want to comment-out.
2. Press Ctrl-V to start block-mode selection.
3. Move down to select the first column of a block of lines.
4. Press I and then the desired comment starter (i.e. #)
5. Press ESC and the insertion will be applied to the whole block.

To uncomment with this techniques follow the directions but instead of I use x to delete the first char.


