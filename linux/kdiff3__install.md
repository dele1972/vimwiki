# kdiff3


## Install

apt-cache search kdiff3
sudo apt-get install kdiff3


## config: .gitconfig

[Using KDiff3 as a Git Diff and Merging Tool](https://docs.kde.org/trunk5/en/extragear-utils/kdiff3/git.html)

`which kdiff3`

vim ~/.gitconfig
[diff]
        tool = kdiff3
[difftool "kdiff3"]
        path = <path to kdiff3 binary in your system>
[difftool]
        prompt = false
        keepBackup = false
        trustExitCode = false
[merge]
        tool = kdiff3
[mergetool]
        prompt = false
        keepBackup = false
        keepTemporaries = false
[mergetool "kdiff3"]
        path = <path to kdiff3 binary in your system>


## see

- see `/home/lederich/wissen-sammler/git - diff and difftool.md`
- see `/home/lederich/wissen-sammler/linux - tool install kdiff3.md` (**this article**)
- see `/home/lederich/wissen-sammler/git - pycharm as git difftool and mergetool.md`

