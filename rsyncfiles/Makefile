.PHONY: print

rsyncfiles := git --git-dir=$$HOME/.rsync/ --work-tree=$$HOME

rsyncfilters_raw := rsyncfilters.txt
rsyncfilters := $(shell cat ${rsyncfilters_raw})

# create list of .rsync-filter files
rsyncfilters.txt:
	find ~/ -type f -name ".rsync-filter" > $@


# usage commands
rf_list:
	@cat rsyncfilters.txt

# make file=.rsync-filter rf_print
rf_print:
	@cat $(file)

rf_zip:
	@zip_rsyncfilter $(file)

# git commands
status:
	$(rsyncfiles) status

add:
	$(rsyncfiles) add -f $(rsyncfilters)

update:
	$(rsyncfiles) add -u

diff:
	$(rsyncfiles) diff

push:
	$(rsyncfiles) push

