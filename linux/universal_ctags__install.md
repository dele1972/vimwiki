# Installation of Universal Ctags (Ubuntu)

This installation guide is based on the one from Trey Harris (see Link-Section).

## 1. Precautions

**Change to the location for storing the project:**

```bash
cd ~/.local/share
```

**Install some needed ressources:**

```bash
sudo apt install \
    gcc make \
    pkg-config autoconf automake \
    python3-docutils \
    libseccomp-dev \
    libjansson-dev \
    libyaml-dev \
    libxml2-dev
```

## 2. Download and build universal-ctags

```bash
$ git clone https://github.com/universal-ctags/ctags.git && cd ctags
```

```bash
./autogen.sh
```

```bash
./configure
```

```bash
make
```

## 3. Install universal-ctags

```bash
sudo make install
```

## 4. Add universal-ctags to Ubuntu ctags alternatives

**check if ctags or etags alternatives already available:**

```bash
update-alternatives --display ctags
update-alternatives --display etags
```

**add just installed ctags to the alternatives:**

```bash
sudo update-alternatives --install /usr/bin/ctags ctags /usr/local/bin/ctags 50 --slave /usr/share/man/man1/ctags.1.gz ctags.1.gz /usr/local/share/man/man1/ctags.1
sudo update-alternatives --install /usr/bin/etags etags /usr/local/bin/ctags 50 --slave /usr/share/man/man1/etags.1.gz etags.1.gz /usr/local/share/man/man1/ctags.1
```

## 5. Check Installation

```bash
echo =ctags =etags
```
--> Output: `/usr/local/bin/ctags /usr/bin/etags`

```bash
readlink -f =etags =ctags
```
--> Output:

```bash
/usr/local/bin/ctags
/usr/local/bin/ctags
```

## 6. use is

```bash
ctags -R .
etags -R .
```

## Links

- Trey Harris: [Installing universal-ctags on Ubuntu](https://gist.github.com/treyharris/e19bb74d72af432dd6984ad9907ae538#installing-universal-ctags-on-ubuntu)
- GitHub: [universal-ctags/ctags Installation](https://github.com/universal-ctags/ctags/blob/master/docs/autotools.rst#building-with-configure-nix-including-gnulinux)
