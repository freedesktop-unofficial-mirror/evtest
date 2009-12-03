
bin_PROGRAMS = evtest
man_pages_src = evtest.txt

if HAVE_LIBXML
bin_PROGRAMS += evtest-capture
AM_CFLAGS = $(XML_CFLAGS)

evtest_capture_LDADD = $(XML_LIBS)
man_pages_src += evtest-capture.txt
evtest_capturedir = $(datadir)/evtest
dist_evtest_capture_DATA = evtest-create-device.xsl
endif

EXTRA_DIST = INSTALL

# man page generation.
if HAVE_DOCTOOLS
man_pages = $(man_pages_src:.txt=.1)

SUFFIXES = .1 .txt .xml

.xml.1:
	@$(XMLTO) man $<

.txt.xml:
	@$(ASCIIDOC) -b docbook -d manpage -o $@ $<

dist_man_MANS = $(man_pages)

EXTRA_DIST += $(man_pages_src) $(man_pages)
CLEANFILES = $(dist_man_MANS)
MAINTAINERCLEANFILES = $(man_pages) *.xml
endif

