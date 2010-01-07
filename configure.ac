# Process this file with autoconf to produce a configure script.
dnl We use the new format of AC_INIT
dnl info --file=autoconf.info --node="Initializing configure" for more info
# Public domain.
AC_INIT([tinycdb], [0.77], [])
AC_PREREQ(2.53)
AC_CONFIG_SRCDIR(cdb.c)
AM_INIT_AUTOMAKE([1.6 dist-bzip2 dist-zip])

AM_MAINTAINER_MODE

# Checks for programs.
AC_PROG_LIBTOOL
AC_PROG_CC
AC_ISC_POSIX

AC_PROG_CPP

AC_PROG_RANLIB
AC_PROG_INSTALL

# Checks for header files.
AC_PATH_XTRA
AC_HEADER_STDC
AC_CHECK_HEADERS([errno.h fcntl.h .h signal.h sys/mman.h sys/stat.h sys/types.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_SIGNAL
AC_TYPE_SIZE_T
AC_C_INLINE

# Checks for library functions.
AC_FUNC_MMAP
AC_FUNC_STAT

AC_CHECK_SIZEOF(long)

AC_CONFIG_FILES([Makefile])

AC_OUTPUT

