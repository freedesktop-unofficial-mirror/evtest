
bin_PROGRAMS = evtest

if HAVE_LIBXML
bin_PROGRAMS += evtest-capture
AM_CFLAGS = $(XML_CFLAGS)

evtest_capture_LDADD = $(XML_LIBS)
endif


man1_MANS = evtest.man
EXTRA_DIST = $(man1_MANS) evtest-generate-device.xsl
