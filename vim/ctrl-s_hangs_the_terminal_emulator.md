# Ctrl-s hangs the terminal emulator

## Quick-Fix

`Ctrl-q`

## Fix

Add (one of) the following to the `~/.bash_profile` or `~/.bashrc` config:

```shell
stty -ixon
stty ixany
stty ixoff -ixon
```

## Source

[StackExchange: Ctrl-s hangs the terminal emulator?](https://unix.stackexchange.com/questions/72086/ctrl-s-hangs-the-terminal-emulator)

## Statement

This feature is called Software Flow Control (XON/XOFF flow control) - see further information on given source link above.
