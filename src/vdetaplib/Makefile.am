pkglib_LTLIBRARIES = libvdetap.la
libexec_PROGRAMS = vdetap

if ENABLE_PROFILE
  AM_CFLAGS = -pg --coverage
  AM_LDFLAGS = -pg --coverage
endif

libvdetap_la_SOURCES = libvdetap.c
libvdetap_la_LDFLAGS = $(AM_LDFLAGS) -avoid-version -export-dynamic -module -Wl,-init -Wl,libvdetap_init -Wl,-fini -Wl,libvdetap_fini
# vdetaplib/libvdetap.c|85| warning: dereferencing type-punned pointer will break strict-aliasing rules
libvdetap_la_CFLAGS = $(AM_CFLAGS) -fno-strict-aliasing

AM_CPPFLAGS = -I$(top_srcdir)/include -DLIBEXECDIR=\"$(libexecdir)\"

vdetap_SOURCES = vdetap.c
vdetap_LDADD = $(top_builddir)/src/common/libvdecommon.la $(top_builddir)/src/lib/libvdeplug.la

EXTRA_DIST = test.c
