################################################################################
#  THIS FILE IS 100% GENERATED BY ZPROJECT; DO NOT EDIT EXCEPT EXPERIMENTALLY  #
#  Read the zproject/README.md for information about making permanent changes. #
################################################################################
# Default target
all-local: doc

# Public programs ("main" tags in project.xml), auto-regenerated:
MAN1 = dafka_console_producer.1 dafka_console_consumer.1 dafka_stored.1 dafka_towerd.1
# Public classes ("class" tags in project.xml), auto-regenerated:
MAN3 = dafka_consumer_msg.3 dafka_producer_msg.3 dafka_producer.3 dafka_consumer.3 dafka_proto.3 dafka_beacon.3 dafka_tower.3 dafka_store.3
# Project overview, written by a human after initial skeleton:
# NOTE: stub doc/dafka.adoc is generated by GSL from project.xml
#       and then comitted to SCM and maintained manually to describe the
#       project (section 7 = Overview, conventions, and miscellaneous).
MAN7 = dafka.7
MAN_DOC = $(MAN1) $(MAN3) $(MAN7)

# Assumption: the single .7 page only covers the project and is maintained
# manually. The SCM-tracked text source file name uses an .adoc extension
# so as not to conflict with generated .txt files (in cases when a "class"
# or a "main" name is same as overall project name).
MAN_TXT = $(MAN7:%.7=%.adoc)

EXTRA_DIST = asciidoc.conf mkman

if INSTALL_MAN
dist_man_MANS = $(MAN_DOC)
endif

if BUILD_DOC
MAN_TXT += $(MAN1:%.1=%.txt)
MAN_TXT += $(MAN3:%.3=%.txt)

DISTCLEANFILES = $(MAN_DOC)

dist-hook : $(MAN_DOC)

SUFFIXES=.txt .adoc .xml .xml7 .1 .3 .7

.txt.xml:
	asciidoc -d manpage -b docbook -f $(srcdir)/asciidoc.conf \
        -adafka_version=@PACKAGE_VERSION@ -o$@ $<
.xml.1:
	xmlto -o $(@D) man $<
.xml.3:
	xmlto -o $(@D) man $<

# Special handling for project overview whose basename may collide
# with a main or class name
.adoc.xml7:
	asciidoc -d manpage -b docbook -f $(srcdir)/asciidoc.conf \
        -adafka_version=@PACKAGE_VERSION@ -o$@ $<
.xml7.7:
	xmlto -o $(@D) man $<

# List of *.txt and *.doc files generated during build from comments
# in project program source files and further processed into manpages.
GENERATED_DOCS =

# No-op, docs and texts are generated by mkman in one shot - just
# make a dependency that can not parallelize and break stuff.
# Also, to be validly processed, the dependency must have SOME payload
.txt.doc:
	@true

GENERATED_DOCS += dafka_consumer_msg.txt dafka_consumer_msg.doc
dafka_consumer_msg.txt: $(top_srcdir)/src/dafka_consumer_msg.c
	"$(srcdir)/mkman" "dafka_consumer_msg" "$(builddir)/dafka_consumer_msg.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_producer_msg.txt dafka_producer_msg.doc
dafka_producer_msg.txt: $(top_srcdir)/src/dafka_producer_msg.c
	"$(srcdir)/mkman" "dafka_producer_msg" "$(builddir)/dafka_producer_msg.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_producer.txt dafka_producer.doc
dafka_producer.txt: $(top_srcdir)/src/dafka_producer.c
	"$(srcdir)/mkman" "dafka_producer" "$(builddir)/dafka_producer.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_consumer.txt dafka_consumer.doc
dafka_consumer.txt: $(top_srcdir)/src/dafka_consumer.c
	"$(srcdir)/mkman" "dafka_consumer" "$(builddir)/dafka_consumer.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_proto.txt dafka_proto.doc
dafka_proto.txt: $(top_srcdir)/src/dafka_proto.c
	"$(srcdir)/mkman" "dafka_proto" "$(builddir)/dafka_proto.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_beacon.txt dafka_beacon.doc
dafka_beacon.txt: $(top_srcdir)/src/dafka_beacon.c
	"$(srcdir)/mkman" "dafka_beacon" "$(builddir)/dafka_beacon.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_tower.txt dafka_tower.doc
dafka_tower.txt: $(top_srcdir)/src/dafka_tower.c
	"$(srcdir)/mkman" "dafka_tower" "$(builddir)/dafka_tower.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_store.txt dafka_store.doc
dafka_store.txt: $(top_srcdir)/src/dafka_store.c
	"$(srcdir)/mkman" "dafka_store" "$(builddir)/dafka_store.txt" "$(srcdir)/.."

### Note: for mains, we keep the source name rather than flattened name:c
### so that the manpages for binary programs match their name, at expense
### of perhaps being built in a subdirectory under doc/.
GENERATED_DOCS += dafka_console_producer.txt dafka_console_producer.doc
dafka_console_producer.txt: $(top_srcdir)/src/dafka_console_producer.c
	mkdir -p "$(builddir)/$(@D)"
	"$(srcdir)/mkman" "dafka_console_producer" "$(builddir)/dafka_console_producer.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_console_consumer.txt dafka_console_consumer.doc
dafka_console_consumer.txt: $(top_srcdir)/src/dafka_console_consumer.c
	mkdir -p "$(builddir)/$(@D)"
	"$(srcdir)/mkman" "dafka_console_consumer" "$(builddir)/dafka_console_consumer.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_stored.txt dafka_stored.doc
dafka_stored.txt: $(top_srcdir)/src/dafka_stored.c
	mkdir -p "$(builddir)/$(@D)"
	"$(srcdir)/mkman" "dafka_stored" "$(builddir)/dafka_stored.txt" "$(srcdir)/.."

GENERATED_DOCS += dafka_towerd.txt dafka_towerd.doc
dafka_towerd.txt: $(top_srcdir)/src/dafka_towerd.c
	mkdir -p "$(builddir)/$(@D)"
	"$(srcdir)/mkman" "dafka_towerd" "$(builddir)/dafka_towerd.txt" "$(srcdir)/.."


clean-local:
	rm -f *.1 *.3 *.7 $(GENERATED_DOCS)

doc: $(GENERATED_DOCS)

else
doc:
	@echo "SKIPPING documentation generation and formatting (BUILD_DOC was not required and/or tools are missing)" >&2
endif

EXTRA_DIST += $(MAN_TXT)
################################################################################
#  THIS FILE IS 100% GENERATED BY ZPROJECT; DO NOT EDIT EXCEPT EXPERIMENTALLY  #
#  Read the zproject/README.md for information about making permanent changes. #
################################################################################
