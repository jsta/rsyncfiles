## rsyncfiles

Manage .rsync-filter files with tools for finding, listing, and archiving targets.

### Setup

```
git clone git@github.com:jsta/rsyncfiles.git
git clone --bare git@github.com:jsta/rsyncfiles.git $HOME/.rsync
alias rsyncfiles='git --git-dir=$HOME/.rsync/ --work-tree=$HOME'
rsyncfiles config --local status.showUntrackedFiles no
rsyncfiles config --local pull.rebase true
rsyncfiles reset --hard

rm ~/README.md
rsyncfiles update-index --skip-worktree README.md
```

### Usage

1. List `.rsync-filter` files

```
make rf_list
```

2. Print the contents of a target file

```
make file=.rsync-filter rf_print
```

3. Zip filtered files
```
make file=.rsync-filter rf_zip
```

### References

https://unix.stackexchange.com/questions/574563/is-there-such-thing-as-an-rsyncignore-file#comment1069834_574563

https://askubuntu.com/a/455196/301014

https://gist.github.com/DarwinAwardWinner/948032
