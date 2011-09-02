AC_PREREQ([2.57])
AC_INIT(evtest,[1.29], [https://bugzilla.freedesktop.org/enter_bug.cgi?product=evtest], evtest)
AM_INIT_AUTOMAKE([foreign dist-bzip2])

AM_CONFIG_HEADER(config.h)
AC_PROG_CC
AC_PROG_INSTALL

PKG_CHECK_MODULES(XML, libxml-2.0, [HAVE_LIBXML=yes], [HAVE_LIBXML=no])
if test x$HAVE_LIBXML = "xno"; then
    AC_MSG_WARN([libxml headers not available. Cannot build evtest-capture.])
fi
AM_CONDITIONAL(HAVE_LIBXML, [test "x$HAVE_LIBXML" = "xyes"])

AC_PATH_PROG(XSLTPROC, [xsltproc])
AM_CONDITIONAL([HAVE_XSLTPROC], [test "x$XSLTPROC" != "x"])
if test "x$XSLTPROC" = "x"; then
	AC_MSG_WARN([xsltproc not found, needed to generate devices.])
fi

AC_ARG_VAR([XMLTO], [Path to xmlto command])
AC_PATH_PROG([XMLTO], [xmlto])
AC_ARG_VAR([ASCIIDOC], [Path to asciidoc command])
AC_PATH_PROG([ASCIIDOC], [asciidoc])
AM_CONDITIONAL([HAVE_DOCTOOLS], [test "x$XMLTO" != "x" && test "x$ASCIIDOC" != "x"])
if test "x$XMLTO" = "x" || test "x$ASCIIDOC" = "x"; then
	AC_MSG_WARN([xmlto or asciidoc not found - cannot create man pages without it])
fi

AC_OUTPUT([Makefile])
