ACLOCAL_AMFLAGS = -I m4
AUTOMAKE_OPTIONS = gnu

bin_PROGRAMS = mib2opennms
mib2opennms_SOURCES = mib2opennms.c
bin_SCRIPTS = rename-mibs.pl

MAINTAINERCLEANFILES = aclocal.m4 config.guess config.sub configure depcomp install-sh ltmain.sh Makefile.in missing config.h.in *~ *.tar.gz

EXTRA_DIST = ChangeLog rename-mibs.pl

if MAKE_RPMS
.PHONY: rpm

rpm: @RPM_TARGET@

EXTRA_DIST += mib2opennms.spec

$(RPM_TARGET): $(DISTFILES)
	${MAKE} dist
	-mkdir -p $(RPM_DIR)/SRPMS
	-mkdir -p `dirname $(RPM_TARGET)`
	$(RPMBUILD_PROG) $(RPM_ARGS) $(RPM_TARBALL)
	@echo "$(RPM_TARGET) created"
endif
