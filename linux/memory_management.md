# linux memory management

## check memory usage

### in realtime with `watch` / `free` (1)

```shell
watch -n 1 free -m
```

### in realtime with `watch` / `cat` (1)

```shell
watch -n 1 cat /proc/meminfo
```

### as output with `free` (3)

```shell
free -h
```

*Note*: The Author of (3) combines all together with multiple free up commands suggested later on ...


## Free Up Unused Memory

### with `sysctl` (1)

*NOTE*: this action won't make your system faster nor it will affect its stability and performance, it will just clean up memory used by the Linux Kernel on caches.

```shell
sudo sysctl -w vm.drop_caches=3
```

### with `sync` / `echo 3` / `tee` (1)

```shell
sudo sync && echo 3 | sudo tee /proc/sys/vm/drop_caches***
```

## Links

- 1: [How to Free up Unused Memory in Ubuntu/Linux Mint](http://www.upubuntu.com/2013/01/how-to-free-up-unused-memory-in.html)
- 2: [free up mem with 3 asterisk](https://askubuntu.com/a/1280347)
- 3: [combination is the key](https://askubuntu.com/a/1189669)

