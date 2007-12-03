AC_PREREQ(2.59)

AC_INIT([mib2opennms], [0.3.1], [http://www.opennms.org/])

RELEASE=1
AC_SUBST([RELEASE])

AC_CONFIG_MACRO_DIR([m4])
AM_CONFIG_HEADER([config.h])
AM_INIT_AUTOMAKE([1.9 foreign])

# don't test c++ and f77 in libtool
m4_ifdef([AC_LIBTOOL_TAGS], [AC_LIBTOOL_TAGS([])])

dnl find and test the C compiler
AC_PROG_CC
AC_LANG_C
        
AC_PROG_INSTALL
AC_PROG_MAKE_SET
               
AC_HEADER_STDC

AM_RPM_INIT
AM_CONDITIONAL(MAKE_RPMS, test x$make_rpms = xtrue)

dnl check libsmi
AC_CHECK_HEADER([smi.h],,AC_MSG_ERROR([mib2opennms requires smi.h]))
AC_CHECK_LIB([smi],[smiInit],,AC_MSG_ERROR([mib2opennms requires libsmi]))

AC_CONFIG_FILES([Makefile mib2opennms.spec])
AC_OUTPUT
