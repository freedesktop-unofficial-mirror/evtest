AC_PREREQ([2.57])
AC_INIT(evtest,[1.23], [], evtest)
AM_INIT_AUTOMAKE([foreign dist-bzip2])

AM_CONFIG_HEADER(config.h)
AC_PROG_CC
AC_PROG_INSTALL

PKG_CHECK_MODULES(XML, libxml-2.0, [HAVE_LIBXML=yes], [HAVE_LIBXML=no])
if test x$HAVE_LIBXML = "xno"; then
    AC_MSG_WARN([libxml headers not available. Cannot build evtest-capture.])
fi
AM_CONDITIONAL(HAVE_LIBXML, [test "x$HAVE_LIBXML" = "xyes"])

AC_OUTPUT([Makefile])
