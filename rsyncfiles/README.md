## rsyncfiles

### TODO

* [x] create a file holding the path to all .rsync-filter files

* [x] track all .rsync-filter files

* [ ] create a bash program to archive (zip) the files pointed to by a given .rsync-filter file

* [ ] symlink to bin folder

### Setup

```
git clone --bare git@github.com:jsta/.rsync.git $HOME/.rsync
alias rsyncfiles='git --git-dir=$HOME/.rsync/ --work-tree=$HOME'
rsyncfiles config --local status.showUntrackedFiles no
# rsyncfiles config --local alias.github '!git add -u && git commit -m "Update rsyncfiles at $(date -u)" && git push'
rsyncfiles config --local pull.rebase true
rsyncfiles reset --hard

rm ~/README.md
rsyncfiles update-index --skip-worktree README.md
```

### References

https://unix.stackexchange.com/questions/574563/is-there-such-thing-as-an-rsyncignore-file#comment1069834_574563
