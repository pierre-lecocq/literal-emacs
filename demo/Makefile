#
# File: Makefile
# Time-stamp: <2015-10-07 08:19:16>
# Copyright (C) 2015 Pierre Lecocq
# Description: Makefile used to generate a lisp file from an org file
#

# Set configuration folder path
SRC_DIR=$(shell pwd)

# Source file (the org file)
SRC_FILE=$(SRC_DIR)/emacs.org

# Destination file (the emacs lisp file)
DEST_FILE=$(SRC_DIR)/emacs.el

# Destination directory where the lisp code will be generated
DEST_DIR=$(SRC_DIR)/lisp

# I love poneys
.PHONY: test build clean love

# Main rule
all: build

# Generate lisp and compile it
build:
	mkdir -p $(DEST_DIR); \
	emacs --batch \
		--eval "(require 'org)" \
		--eval "(org-babel-load-file \"$(SRC_FILE)\")"

# Testing is doubting
test:
	emacs -Q -l $(DEST_FILE)

# Housework
clean:
	rm -rf $(DEST_FILE) $(DEST_DIR)

# Because "make love" is important
love: clean build
