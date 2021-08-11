# regex - vim - Delete all lines containing duplicate words in one line

## Solution

```vim
:g/\(^\<\w\+\>\)\_s*\<\1\>\s/d
```

## Explanation

### Delete all lines containing a pattern

[Delete all lines containing a pattern](https://vim.fandom.com/wiki/Delete_all_lines_containing_a_pattern)

```vim
\(\<\w\+\>\)\_s*\<\1\>
```

### Finding duplicate words

[Finding duplicate words](https://vim.fandom.com/wiki/Search_patterns#Finding_duplicate_words)

```vim
\(^\<\w\+\>\)\_s*\<\1\>\s
```
