# Vim - reload current file

## Solution (current file)

```vi
:e
```

This is short for ~:edit`. Use `:edit!` to discard local changes.

## Solution (all buffers)

```vi
:bufdo :e
```

or

```vi
:bufdo :e!
```

## Possible interesting too

```vi
" Compare buffer with saved version
nnoremap gd :DiffSaved<CR>
```

### Links

- https://vi.stackexchange.com/questions/444/how-do-i-reload-the-current-file
  - How do I reload the current file?
  - 2015-02-06, 200_success
