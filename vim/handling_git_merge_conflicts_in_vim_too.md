Git: Handling Merge Conflicts Using "Ours" and "Theirs"


https://howchoo.com/git/git-merge-conflicts-rebase-ours-theirs#using-ours-theirs-during-a-rebase

 	git merge master 	git rebase master
Keep changes from master 	--theirs 	--ours
Keep changes from feature 	--ours 	--theirs


# git log graph (https://stackoverflow.com/questions/1838873/visualizing-branch-topology-in-git)


git log --graph --abbrev-commit --simplify-by-decoration --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'

git log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(auto)%d%C(reset)'

git log --graph --full-history --all --color --date=short --pretty=format:"%x1b[31m%h%x09%x1b[32m%d%x1b[0m%x20%ad %s"

## gitk

sudo apt-get install gitk 


# VIM (fugitive)

## 3-way diff

[source](http://vimcasts.org/episodes/fugitive-vim-resolving-merge-conflicts-with-vimdiff/)

### What is target/merge branch?

- **‘target’ branch**
  - is the one that is active when you run git merge.
  - Or in other words, it’s the HEAD branch.
- **‘merge’ branch**
  - is the one that is named in the git merge command.

### Scenario

```bash
(feature) $ git checkout master
 (master) $ git merge feature
```

- **‘target’ branch**
  - `(master)`
- **‘merge’ branch**
  - `(feature)` branch is merged into target, making it the merge branch.



MERGE BRANCH  +----o--o------+
(feature)                     \
                               \
                                \
TARGET BRANCH +-o----------o-----+---+
(master)                             HEAD

### The 3-way difftool

- the left window contains the version from the target branch (mostly in my case: master)
- the middle window contains the working copy of the file, complete with conflict markers
- the right window contains the version from the merge branch (the branch which I am currently working on)

+----------+----------+----------+
|  target  | working  |   merge  |
|  (HEAD)  |   copy   |          |
|          |          |          |
+--------------------------------+
| bufspec: |          | bufspec: |
|          |          |          |
|   //2    |          |   //3    |
|          |          |          |
|          |          |          |
|          |          |          |
|          |          |          |
+----------+----------+----------+

- work in the middle window
- `]c` jumps to next conflict
- `[c` jumps to prev conflict
- `:diffupdate` to recalculate the diff colors (for solved hunks)
- `:diffget //2` takes the hunk of the left side (master)
- `:diffget //3` takes the hunk of the right side (current branch)
- `:only` close all windows apart from the current one
- `:Gwrite[!]` write the current file to the index (and exits vimdiff mode when present)

