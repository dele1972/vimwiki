
https://gist.github.com/treyharris/e19bb74d72af432dd6984ad9907ae538


mkdir ~/src
cd ~/src
git clone https://github.com/universal-ctags/ctags.git
cd ctags
./autogen.sh
make
sudo make install
update-alternatives --display ctags
update-alternatives --display etags
sudo update-alternatives --install /usr/bin/ctags ctags /usr/local/bin/ctags 50 --slave /usr/share/man/man1/ctags.1.gz ctags.1.gz /usr/local/share/man/man1/ctags.1
sudo update-alternatives --install /usr/bin/etags etags /usr/local/bin/ctags 50 --slave /usr/share/man/man1/etags.1.gz etags.1.gz /usr/local/share/man/man1/ctags.1
% echo =ctags =etags
/usr/local/bin/ctags /usr/bin/etags
% readlink -f =etags =ctags
/usr/local/bin/ctags
/usr/local/bin/ctags

ctags -R .
etags -R .

