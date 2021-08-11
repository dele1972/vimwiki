Install Firefox gecko Driver (Linux/Ubuntu)

download latest release --> https://github.com/mozilla/geckodriver/releases

sudo sh -c 'tar -x geckodriver -zf geckodriver-v0.24.0-linux64.tar.gz -O > /usr/bin/geckodriver'

sudo chmod +x /usr/bin/geckodriver

export PATH=$PATH:/path-to-extracted-file/.

https://askubuntu.com/a/871077   How to install geckodriver in Ubuntu? [duplicate]
https://askubuntu.com/a/923317   Install Geckodriver and Chromedriver
https://medium.com/@sonaldwivedi/downloading-and-setting-up-geckodriver-87873e25207c

ACHTUNG - für Downloads von der Konsole:
o.g. Link ist lediglich ein Weiterleitungslink unter
https://npm.taobao.org/mirrors/geckodriver/
gibt es auch direkte cdn links - diese müssten aber auch einmal angeklickt werden damit man den richtigen Link bekommt:

	curl -O https://cdn.npm.taobao.org/dist/geckodriver/v0.26.0/geckodriver-v0.26.0-linux64.tar.gz
