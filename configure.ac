dnl ner: configure.ac

AC_PREREQ([2.59])

AC_INIT([ner], [0.0.1], [mforney@mforney.org])
AM_INIT_AUTOMAKE([foreign -Wall -Werror])
AC_LANG([C++])

AC_CONFIG_SRCDIR([src/ner.cc])
AC_CONFIG_MACRO_DIR([m4])

m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES([yes])])

AX_CXX_COMPILE_STDCXX_11
PKG_PROG_PKG_CONFIG([0.9.0])

dnl Check for libraries {{{
PKG_CHECK_MODULES([gmime], [gmime-2.4])
PKG_CHECK_MODULES([gio], [gio-2.0])
PKG_CHECK_MODULES([yaml_cpp], [yaml-cpp >= 0.3.0])
AC_CHECK_LIB(notmuch, notmuch_database_open,,
    [AC_MSG_ERROR([ner requires libnotmuch])])
AC_CHECK_LIB(ncursesw, initscr,,
    [AC_MSG_ERROR([ner requires ncursesw])])

AC_CHECK_HEADERS(ncursesw/ncurses.h,,
    [AC_CHECK_HEADERS(ncurses/ncurses.h,,
        [AC_CHECK_HEADERS(ncurses.h)])])
dnl }}}

AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile src/Makefile])
AC_OUTPUT

