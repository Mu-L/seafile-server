AM_CFLAGS = -DPKGDATADIR=\"$(pkgdatadir)\" \
	-DPACKAGE_DATA_DIR=\""$(pkgdatadir)"\" \
	-DSEAFILE_SERVER \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/lib \
	-I$(top_builddir)/lib \
	-I$(top_srcdir)/common \
	@SEARPC_CFLAGS@ \
	@GLIB2_CFLAGS@ \
	@FUSE_CFLAGS@ \
	@MYSQL_CFLAGS@ \
	-Wall

bin_PROGRAMS = seaf-fuse

noinst_HEADERS = seaf-fuse.h seafile-session.h repo-mgr.h

seaf_fuse_SOURCES = seaf-fuse.c \
                    seafile-session.c \
		    file.c \
		    getattr.c \
                    readdir.c \
                    repo-mgr.c \
                    ../common/block-mgr.c \
                    ../common/user-mgr.c \
                    ../common/group-mgr.c \
                    ../common/org-mgr.c \
                    ../common/block-backend.c \
                    ../common/block-backend-fs.c \
                    ../common/branch-mgr.c \
                    ../common/commit-mgr.c \
                    ../common/fs-mgr.c \
                    ../common/log.c \
                    ../common/seaf-db.c \
                    ../common/seaf-utils.c \
                    ../common/obj-store.c \
                    ../common/obj-backend-fs.c \
                    ../common/obj-backend-riak.c \
                    ../common/seafile-crypt.c \
                    ../common/password-hash.c

seaf_fuse_LDADD = @GLIB2_LIBS@ @GOBJECT_LIBS@ @SSL_LIBS@ @LIB_RT@ @LIB_UUID@ \
                  -lsqlite3 @LIBEVENT_LIBS@ \
		  $(top_builddir)/common/cdc/libcdc.la \
		  @SEARPC_LIBS@ @JANSSON_LIBS@ @FUSE_LIBS@ @ZLIB_LIBS@ \
		  @LDAP_LIBS@ @MYSQL_LIBS@ -lsqlite3 @ARGON2_LIBS@

