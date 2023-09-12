SHELL:=/bin/bash

init:
	python3 -m venv --without-pip ./venv
	source ./venv/bin/activate && python3 -m ensurepip --upgrade
	source ./venv/bin/activate && pip3 install ansible

clean:
	rm -rf ./venv
	rm -rf ./cache

reset: clean init
