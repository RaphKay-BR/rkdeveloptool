dnl Copyright (C) 2017  Trevor Woerner <twoerner@gmail.com>

AC_INIT([Rockchip rkdeveloptool], 1.33, [Eddie Cai <eddie.cai.linux@gmail.com>], rkdeveloptool)
AC_PREREQ([2.68])
AC_CONFIG_SRCDIR(main.cpp)
AC_CONFIG_AUX_DIR(cfg)
AM_INIT_AUTOMAKE([foreign no-dist-gzip dist-bzip2 1.9])
AM_CONFIG_HEADER(cfg/config.h)

SUBDIRS=""

AC_PROG_CPP
AC_PROG_CXX
AC_PROG_CXXCPP
AC_PROG_MAKE_SET
AC_PROG_INSTALL
AC_PROG_LN_S

AC_CANONICAL_HOST
case "$host_os" in
	freebsd*)
		CPPFLAGS="$CFLAGS -I/usr/local/include"
		LDFLAGS="$LDFLAGS -L/usr/local/lib -liconv"
		;;
	openbsd*)
		CPPFLAGS="$CFLAGS -I/usr/local/include"
		LDFLAGS="$LDFLAGS -L/usr/local/lib"
		;;
	*)
		;;
esac

AC_SEARCH_LIBS(iconv, iconv)

PKG_CHECK_MODULES(LIBUSB1,libusb-1.0)

AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([cfg/Makefile])

AC_OUTPUT
