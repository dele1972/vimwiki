# Regular Expressions (and Vim)

## An introduction to regular expressions in Vim

[source][1]

This is a brief overview that covers probably 80% of typical regular expression use cases for refactoring applications.

I had a brain fart about halfway through, if you want to select a region based on regular expressions, your command is this:

```vim
:g/[pattern1]/ s/[pattern-to-sub]/[replacement]/[flags]
```

### Index

- ~[1:45](https://youtu.be/4KwsijqA7tQ?t=105) start: open and introduce flights.md as a demonstration base
- [1:58](https://youtu.be/4KwsijqA7tQ?t=118) The first thing: substitution with **global search and replace**
  - `:%s/ind/RSW`
    - `%` - all lines in the file ...
    - `s/ind` ... substitute *ind*
    - `/RSW` ... with *RSW*
- [2:33](https://youtu.be/4KwsijqA7tQ?t=153) Introduce traces Vim Plugin
- [3:23](https://youtu.be/4KwsijqA7tQ?t=203) **substitute within a range** (*vsual bock mode*)
  - `:'<,'>s/ind/RSW`
    - `'<,'>` - from start up to end of visual block ...
    - `s/ind` ... substitute *ind*
    - `/RSW` ... with *RSW*
    - hit `q` and `:` for reuse again with editing option
- [4:22](https://youtu.be/4KwsijqA7tQ?t=262)  **substitute within a range** (*line numbers*)
  - `:4,9s/IND/RSW`
    - `4,9` - from line number 4 to 9 ...
    - `s/IND` ... substitute *IND*
    - `/RSW` ... with *RSW*
- [4:47](https://youtu.be/4KwsijqA7tQ?t=287) **global and confirmation**
  - `:%s/0/1` replaces only the first match of `0` of each line with `1`
  - `:%s/0/1/g` replaces ALL (global) matches of `0` of each line with `1`
    - `/g` flag for global matches
  - `:%s/0/1/gc` find all matches and ask for replacing (**confirmation**)
    - `/c` flag for confirmation
- [5:50](https://youtu.be/4KwsijqA7tQ?t=350) **special characters**
  - `:%s/\w`
    - `\w` find a word (a letter without space)
  - `:%s/\s`
    - `\s` find space characters
  - `:%s/\d`
    - `\d` find digits
- [6:22](https://youtu.be/4KwsijqA7tQ?t=382) **a set with 'how many'**
  - `:%s/\d\{4}` find four consecutive digits
    - `\{4}` four consecutive
  - `:%s/\d\+` find one or more (consecutive) digits
    - `\+` one or more (consecutive)
  - `:%s/\s\*` find zero or more (consecutive) digits
    - `\s\*` zero or more (consecutive)
  - `:%s/PHX\s*-\s*/RSW-` replace *PHX* which is followed by zero or more spaces and a '*-*' and replace it by *RSW-*
- [8:23](https://youtu.be/4KwsijqA7tQ?t=503) **sustitute 'OK' way**
  - `:%s/American 1/American 2` replaces *American 1* with *American 2*
- [8:58](https://youtu.be/4KwsijqA7tQ?t=538) **substitute with groups**
  - `:%s/\(American \)0/\13` replace *American 0* by *American 3*
    - `/\(American \)0` search for *American 0* but ...
      - `\(American \)` ... define '*American *' as group 1
    - `/\13` ... replace by group 1 followed by 3
- [9:58](https://youtu.be/4KwsijqA7tQ?t=598) **substitute a pattern with a pre match** something that begins with ... (what you really want to do)
  - `:%s/American \zs\d\ze/3` replace 'American *0*' by 'American *3*' (only *0* is replaced by *3* but with the start criterion 'American '
    - `:%s/American ` find American
    - `\zs` but start match pattern just now
    - `\d` find a digit
    - `\ze` set the end of the pattern
    - `/3` and replace it with 3
- [10:46](https://youtu.be/4KwsijqA7tQ?t=646) **specify the range** - example messed up :(
- [12:20](https://youtu.be/4KwsijqA7tQ?t=740) **`.zsh_history` example**
  - NOTE: It was pointed out to me that my history example would BREAK if the commands include a semicolon.  This is absolutely correct.  The date capture group could be done like this instead: 
    - `(:\s+\d*:\d;)`
    - ... or is a little more sly way `(:.\{-};)`

### Sources

[1]: https://youtu.be/4KwsijqA7tQ (YouTube Video, *"An introduction to regular expressions in Vim"*, by IntermediateVim, 15.02.2020)
[2]: https://github.com/markonm/traces.vim (recommend Vim PlugIn: traces)
[3]: https://www.reddit.com/r/vim/comments/f0iwrk/my_personal_list_of_vim_tips/fgvbdid/?context=3 (Blog Article, *"My personal list of vim tips"*, by u/antoyo, 2020-02-08)
[4]: http://vimregex.com/ (Vim Regex Tutorial)
[5]: http://vimregex.com/#metacharacters (recommend Chapter: *"4.2 'Escaped' characters or metacharacters"*)
[6]: https://vim.fandom.com/wiki/Ranges (Vim Tips Wiki, Chapter *"Ranges"*)

