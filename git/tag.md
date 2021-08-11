# git tag

https://www.atlassian.com/git/tutorials/inspecting-a-repository/git-tag

## create

### Annotated Tags

- stored as full objects in the Git database
- To reiterate, They store extra meta data such as: the tagger name, email, and date
- for security, annotated tags can be signed and verified with GNU Privacy Guard (GPG)
- Suggested best practices for git tagging is to prefer annotated tags over lightweight so you can have all the associated meta-data.

`git tag -a :TAG -m "Message"`

### Lightweight tag

- created with the absence of the -a, -s, or -m options
- create a new tag checksum and store it in the .git/ directory of the project's repo

`git tag v1.0`

## Share/Push

`git push origin v1.0`

## Delete Tag

### remote

`git push --delete origin v1.0`

### local

`git tag --delete v1.0`


