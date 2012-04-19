remake
======

remake is a simple erlang script that can be used from emacs
or from command line, simple as:

    remake

The effect of the command is to look for a Makefile or a rebar.config
by search starting from current directory and upwards to the root directory,
not including root it self.

The output from remake is translated in away that make filenames
be relative current directory, making remake ideal to be used
from emacs.

Clone remake.git anywhere and make sure remake can be found in PATH.

In .emacs add this line to make remake the default make command

    (setq compile-command "remake")

Features
========

    remake foo.c

Compile the file foo.c with gcc and link the output to 'foo'.

    remake foo.erl

Uses erlc to compile the Erlang module foo.

    remake doc

If rebar.config is found the run "rebar doc" in that directory or
if Makefile is found the run "make doc". In general the arguments
to remake is passed to either rebar or make. Which means that only
some combination are useful for both cases.
