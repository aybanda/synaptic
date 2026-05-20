
AM_CPPFLAGS = -I${top_srcdir}/common -I${top_srcdir}/gtk \
	@GTK_CFLAGS@ @VTE_CFLAGS@ @LP_CFLAGS@ $(LIBTAGCOLL_CFLAGS) $(LIBEPT_CFLAGS) -O0 -g3

noinst_PROGRAMS = test_rpackage test_rpackageview test_gtkpkglist test_rpackagefilter
check_PROGRAMS = test_deb822_integration
TESTS = $(check_PROGRAMS)

LDADD = \
	${top_builddir}/common/libsynaptic.a\
	-lapt-pkg -lX11 @RPM_LIBS@ @DEB_LIBS@ \
	@GTK_LIBS@ @VTE_LIBS@ @LP_LIBS@\
	-lpthread $(LIBEPT_LIBS)

test_rpackage_SOURCES= test_rpackage.cc

test_rpackagefilter_SOURCES= test_rpackagefilter.cc

test_rpackageview_SOURCES= test_rpackageview.cc

test_gtkpkglist_SOURCES= test_gtkpkglist.cc \
	${top_srcdir}/gtk/rgpackagestatus.cc\
	${top_srcdir}/gtk/rgutils.cc\
	${top_srcdir}/gtk/rgpkgtreeview.cc\
	${top_srcdir}/gtk/gtkpkglist.cc

test_deb822_integration_SOURCES = test_deb822_integration.cc
test_deb822_integration_LDADD = $(LDADD) -lgtest

CLEANFILES= $(wildcard *_wrap.*) $(wildcard *~)
