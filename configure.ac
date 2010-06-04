# Process this file with autoconf to produce a configure script.

# Sets up package and initializes auto*.
AC_INIT([MP3FS], [0.14])
AC_CONFIG_SRCDIR([src/mp3fs.c])
AC_CONFIG_AUX_DIR([config])
AM_INIT_AUTOMAKE([foreign])
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

# Checks for programs.
AC_PROG_CC

# Checks for libraries.
AC_CHECK_LIB([mp3lame], [lame_init],, [AC_MSG_ERROR([You must have liblame-dev installed to build mp3fs.])])
AC_CHECK_LIB([FLAC], [FLAC__stream_decoder_new],, [AC_MSG_ERROR([You must have libflac-dev installed to build mp3fs.])])

# Checks for header files.
AC_CHECK_HEADER([lame/lame.h],, [AC_MSG_ERROR([You must have liblame-dev installed to build mp3fs.])])
AC_CHECK_HEADER([FLAC/stream_decoder.h],, [AC_MSG_ERROR([You must have libflac-dev installed to build mp3fs.])])

# Checks for packages which use pkg-config.
PKG_CHECK_MODULES([fuse], [fuse >= 2.6.0])
PKG_CHECK_MODULES([id3tag], [id3tag])
#PKG_CHECK_MODULES([flac], [flac >= 1.1.3]) # To be enabled later

# Debug option
AC_ARG_ENABLE([debug], [AS_HELP_STRING([--enable-debug], [Enable debug output])], [AC_DEFINE([__DEBUG__])])

# Large file support
AC_SYS_LARGEFILE

# Outputs resulting files.
AC_CONFIG_FILES([Makefile
                 src/Makefile])
AC_OUTPUT