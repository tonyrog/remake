#@BEGIN-ERL_SRC-DEFAULT-RULES@
ERLC=$(shell which erlc)
ERLC_FLAGS=-MMD -MF .$<.d -I ../.. +debug_info
ERL_SOURCES=$(wildcard *.erl)
ERL_OBJECTS=$(ERL_SOURCES:%.erl=../ebin/%.beam)
ALL_OBJECTS=$(ERL_OBJECTS)

all: $(ALL_OBJECTS)

clean:
	rm -f $(ALL_OBJECTS) *.core .*.d

../ebin/%.beam: %.erl
	$(ERLC) $(ERLC_FLAGS) -o ../ebin $<

-include .*.d
#@END-ERL_SRC-DEFAULT-RULES@
