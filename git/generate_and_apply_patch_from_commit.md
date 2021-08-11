https://stackoverflow.com/a/6658352


git format-patch -1 HEAD		# generate patch from last (-1) commit
git format-patch -1 <sha>		# generate patch from commit


git apply --stat file.patch		# show stats
git apply --check file.patch		# check for error before applying
git am < file.patch			# apply the patch finally


This command also works for just a specific file(s) from the commit: git format-patch -1 <sha> path/to/file.js This will create a patch only containing the diffs for the file.js – Kristóf Dombi
