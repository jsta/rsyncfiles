rsyncfiles := git --git-dir=$$HOME/.rsync/ --work-tree=$$HOME

rsyncfilters_raw := rsyncfilters.csv
rsyncfilters := $(shell cat ${rsyncfilters_raw})

rsyncfilters.csv:
	find ~/ -type f -name ".rsync-filter" > $@

status:
	$(rsyncfiles) status

add:
	$(rsyncfiles) add -f $(rsyncfilters)