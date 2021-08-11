# linux swap file management (memory)

From Ubuntu 18.04 onwards, a swapfile rather than a dedicated swap partition is used (except when LVM is used). The swap file is named "swapfile".

## change size

[source](https://askubuntu.com/a/1075516)

### 1. Disable the swap file and delete it

```shell
sudo swapoff /swapfile
sudo rm  /swapfile
```

### 2. Create a new swap file of the desired size (4GB)

Determine the size of your swap file. If you want to make a 4 GB swap file, you will need to write 4 * 1024 blocks of 10242 bytes (= 1 MiB). That will make your count equal to 4 * 1024 = 4096.

4GB is recommended by [this article](https://linuxize.com/post/how-to-add-swap-space-on-ubuntu-20-04/).

Create the file of this size with the command:

```shell
sudo dd if=/dev/zero of=/swapfile bs=1M count=4096
```

### 3. Assign it read/write permissions for root only (not strictly needed, but it tightens security)

```shell
sudo chmod 600 /swapfile
```

### 4. Format the file as swap

```shell
sudo mkswap /swapfile
```

The file will be activated on the next reboot.

#### Activate the new swap for the current session:

```shell
sudo swapon /swapfile
```

### Check the swap that is available

(no root permissions needed)

```shell
swapon -s
```


