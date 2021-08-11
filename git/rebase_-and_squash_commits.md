# rebase

if you

- need the latest commits of the branched branch
- squashing commits(-messages)


## rebase to the top of the branched branch

[source](https://womanonrails.com/git-rebase-onto)

Before                            After
A---B---C---F---G (HEAD master)   A---B---C---F---G (master)
         \                                         \
          D---E (next-feature)                      D'---E' (HEAD next-feature)


`git rebase master next-feature`

or if you already on the next-feature branch:

`git rebase master`


## squashing commits(-messages)

[source](https://www.internalpointers.com/post/squash-commits-into-one-git)

1. `git rebase --interactive [commit-hash]`

Where [commit-hash] is the hash of the commit just (one) before the first one you want to rewrite from.

2. `git push --force`


