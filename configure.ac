AC_PREREQ([2.64])

AC_INIT([rules],
        [208],
        [http://bugs.are.everywhere],
        [rules],
        [http://www.example.com])

AC_PREFIX_DEFAULT([/usr])
AM_INIT_AUTOMAKE([foreign 1.11 silent-rules tar-pax no-dist-gzip dist-xz subdir-objects])
AM_SILENT_RULES([yes])

AC_PROG_MKDIR_P
AC_PROG_SED

AC_ARG_WITH([rootprefix],
         AS_HELP_STRING([--with-rootprefix=DIR], [rootfs directory prefix for config files and kernel modules]),
         [], [with_rootprefix=${ac_default_prefix}])
AC_SUBST([rootprefix], [$with_rootprefix])

AC_OUTPUT([Makefile])
AC_MSG_RESULT([
        $PACKAGE_NAME $VERSION

        prefix:                  ${prefix}
        rootprefix:              ${rootprefix}
        rules:                   ${rootprefix}/lib/udev/rules.d
])
