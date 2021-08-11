https://wiki.linuxmuster.net/archiv/entwicklung:meta:git-tutorial:git-local-fix-last-commit

revert last local commit
git reset --soft HEAD^		# HEAD^ is for last commmit, HEAD^^ or HEAD~2 for the last 2 commits
				# changes of commit will be on stage like before committing changes

git reset --hard HEAD^		# revert last local commit (all changes will be gone!)


