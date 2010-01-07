#! /usr/bin/make -rf
# Public Domain

lib_LTLIBRARIES = libcdb.la libnss_cdb.la
bin_PROGRAMS = cdb cdb-shared

libcdb_la_SOURCES = cdb_init.c cdb_find.c cdb_findnext.c cdb_seq.c cdb_seek.c \
			cdb_unpack.c \
			cdb_make_add.c cdb_make_put.c cdb_make.c cdb_hash.c

libnss_cdb_la_SOURCES = nss_cdb.c nss_cdb-passwd.c nss_cdb-group.c nss_cdb-spwd.c

libnss_cdb_la_LDFLAGS = --version-script=nss_cdb.map

cdb_SOURCES = cdb.c
cdb_shared_SOURCES = cdb.c

cdb_LDADD = libcdb.la
cdb_shared_LDFLAGS = -L$(top_srcdir) -lcdb

include_HEADERS = cdb.h cdb_int.h nss_cdb.h

dist_man_MANS = cdb.3 cdb.1 cdb.5
dist_sysconf_DATA = nss_cdb-Makefile

test tests check: cdb
	sh ./tests.sh ./cdb > tests.out 2>&1
	diff tests.ok tests.out
	@echo All tests passed
test-shared tests-shared check-shared: cdb-shared
	sed 's/^cdb: /cdb-shared: /' <tests.ok >tests-shared.ok
	LD_LIBRARY_PATH=. sh ./tests.sh ./cdb-shared > tests.out 2>&1
	diff tests-shared.ok tests.out
	rm -f tests-shared.ok
	@echo All tests passed
