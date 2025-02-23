#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2019 Alexander Pyhalov
#

BUILD_BITS=64
BUILD_STYLE=justmake

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=	pg_repack
COMPONENT_VERSION=	1.4.8
COMPONENT_SUMMARY=	pg_repack - utility to reorganize PostgreSQL tables on-line
COMPONENT_SRC=	$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).zip
COMPONENT_ARCHIVE_HASH= sha256:5033da618b169095b1f601b267b889407b1a20e567af5ac3524fda3d10f82dfb
COMPONENT_ARCHIVE_URL=	https://api.pgxn.org/dist/pg_repack/$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL=	https://reorg.github.io/pg_repack/
COMPONENT_FMRI=	database/postgres-14/pg_repack
COMPONENT_CLASSIFICATION=	System/Databases
COMPONENT_LICENSE=	BSD
COMPONENT_LICENSE_FILE=	COPYRIGHT

PG_VERSION=	14
# Don't depend on host default pg_config
# Note, for PostgreSQL >= 9.6 $(PG_HOME)/bin contains 64-bit files
PATH=		$(PG_HOME)/bin:/usr/sbin:/usr/bin

TEST_TARGET=$(NO_TESTS)

include $(WS_MAKE_RULES)/common.mk

# Manually added build dependencies
REQUIRED_PACKAGES += database/postgres-14/developer

# Auto-generated dependencies
REQUIRED_PACKAGES += $(PG_LIBRARY_PKG)
REQUIRED_PACKAGES += database/postgres-14
REQUIRED_PACKAGES += system/library
