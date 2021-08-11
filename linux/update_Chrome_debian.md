# linux - update Chrome (deb)

```bash
wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
```

```bash
echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | sudo tee /etc/apt/sources.list.d/google-chrome.list
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install google-chrome-stable
```

- see `linux - install chromedriver` too
- [How to update Chrome in Ubuntu 20.04](https://askubuntu.com/a/1276010)
