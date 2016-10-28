# Makefile to create mobile versions of the Scrum Guide
#
# Examples:
#
#  make epup
#  make mobi
#
# Prerequisites:
#
# pandoc installed and available on PATH
# kindlegen installed and available on PATH
#
# More information: http://bit.do/mobile-scrum-guide

guide = ./guides/scrum-guide

all: download epub mobi

download:
	-mkdir ./guides/
	curl http://scrumguides.org/scrum-guide.html -z $(guide).html -o $(guide).html

html: download

rst: download
	pandoc $(guide).html -o $(guide).rst

epub: download
	pandoc $(guide).html -o $(guide).epub

mobi: epub
	kindlegen $(guide).epub

clean:
	-rm -f ./guides/**