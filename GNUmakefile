TIME                                   := $(shell date +%s)
export TIME
all: codespell say listen
say:
	say -f README.md -o README.aiff
codespell:
	codespell --skip="*.aiff,.git" > spellcheck.log
listen: say
	open README.aiff
push: say codespell
	git add -f *
	git add -f .github
	git commit -m "$(TIME)" --allow-empty
	git push -f origin +master:master
