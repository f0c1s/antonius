#
# hdeps/Makefile
#
# The ../var/header.mk file contains the dependencies among
# header files.
#
# The 'all' target builds a set of timestamp files, one per
# header file, that is more recent than the header file itself
# and all header files that it depends on (recursively).


ifeq ($(wildcard *.mk), header.mk) 
include header.mk
endif


.PHONY: all clean distclean


HEADERS=$(wildcard ../include/*.hrl)
TIMESTAMPS=$(HEADERS:../include/%.hrl=%.t)


$(TIMESTAMPS): %.t: ../include/%.hrl
	touch $@


all: $(TIMESTAMPS)


clean:
	rm -f *.t header.mk


distclean: clean
