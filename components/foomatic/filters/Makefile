#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# Copyright (c) 2011, 2012, Oracle and/or its affiliates. All rights reserved.
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		foomatic-filters
COMPONENT_VERSION=	4.0.17
COMPONENT_REVISION=	3
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
    sha256:a2e2e53e502571e88eeb9010c45a0d54671f15707ee104f5c9c22b59ea7a33e3
COMPONENT_ARCHIVE_URL=	http://www.openprinting.org/download/foomatic/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL=	http://www.linuxfoundation.org/collaborate/workgroups/openprinting/database/foomatic/

TEST_TARGET=$(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

CONFIGURE_OPTIONS +=	--prefix=$(USRLIBDIR)/lp
CONFIGURE_OPTIONS +=	--sysconfdir=$(ETCDIR)/gnu
CONFIGURE_OPTIONS +=	--bindir=$(USRLIBDIR)/lp/bin
CONFIGURE_OPTIONS +=	--with-echo=wecho
CONFIGURE_OPTIONS +=	--with-file-converter="a2ps -1 -q -c -B @@--medium=@@PAGESIZE@@ -o -"
CONFIGURE_OPTIONS +=	--with-execpath=$(USRLIBDIR)/lp/bin:$(USRBINDIR):$(BINDIR)
CONFIGURE_OPTIONS +=	CFLAGS="$(CFLAGS)"
CONFIGURE_OPTIONS +=	A2PS=$(USRBINDIR)/a2ps

COMPONENT_PRE_CONFIGURE_ACTION = ($(CLONEY) $(SOURCE_DIR) $(@D))

# Auto-generated dependencies
REQUIRED_PACKAGES += print/filter/a2ps
REQUIRED_PACKAGES += runtime/perl
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/libdbus
REQUIRED_PACKAGES += system/library/math
