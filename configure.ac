AC_INIT([dirty_garden], [1.0.0], [devel@faemiyah.fi])

AC_CANONICAL_BUILD
AC_CANONICAL_HOST
AC_CANONICAL_TARGET

AM_INIT_AUTOMAKE([dist-bzip2])

AC_CHECK_C99

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET

AC_COMPILE_MODE([MODE_DEBUG])
AC_CONDITIONAL_DEFINE([USE_LD], [yes])

AC_C_BIGENDIAN([], [], [AC_MSG_ERROR([could not determine endianness])])

# Checks for header files.
AC_CHECK_HEADERS([float.h inttypes.h limits.h stddef.h stdint.h stdlib.h string.h wchar.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_INT16_T
AC_TYPE_INT32_T
AC_TYPE_INT64_T
AC_TYPE_INT8_T
AC_TYPE_SIZE_T
AC_CHECK_HEADER_STDBOOL
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T
AC_CHECK_TYPES([ptrdiff_t])

AC_INCORPORATE_LIBPNG([1.2.0], [HAVE_LIBPNG], [no])
AC_INCORPORATE_OPENGL([HAVE_OPENGL], [yes])
AC_INCORPORATE_SDL([1.2.7], [HAVE_SDL], [yes])
AC_ADD_CCFLAG([-flto])
AC_ADD_LDFLAG([-flto])
AC_ADD_LIB([-lm])
AC_ADD_LIB([-ldl])

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([strerror])

AC_CONFIG_FILES([Makefile src/Makefile])
AC_OUTPUT

echo "
Configuration for $PACKAGE_TARNAME $PACKAGE_VERSION:
	Target system:            $target
	Enable debug:             $MODE_DEBUG
	Enable optimizations:     $optimizations
	Compiler flags:           $CFLAGS
	Linker flags:             $LDFLAGS
	Libs:                     $LIBS
	Install prefix:           $prefix
Type 'make' to build and 'make install' to install $PACKAGE."
