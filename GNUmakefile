TIME                                   := $(shell date +%s)
export TIME
all: codespell say listen
say:
	say -f README.md -o README.aiff
codespell:
	codespell > spellcheck.log
listen: say
	open README.aiff
push: say codespell
	git add -f *
	git commit -m "$(TIME)" --allow-empty
	git push -f origin +master:master
