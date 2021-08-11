get actual remote origin url
============================
	git config --get remote.origin.url

	https://stackoverflow.com/a/4089452

set actual remote origin url and set upstream to origin/master branch
=====================================================================
	git remote set-url origin new.git.url/here
	git branch -u origin/master
	https://stackoverflow.com/a/2432799

	git remote set-url origin https://github.com/dele1972/angular-testing.git
	git branch -u origin/master

	git remote set-url origin https://gitlab.hornetsecurity.com/pdc/frontend-research/angular-unittest.git
	git branch -u origin/master


https://gitlab.hornetsecurity.com/pdc/hse-component/ngx-charts
