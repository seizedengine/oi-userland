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

#
# Copyright (c) 2012, Oracle and/or its affiliates. All rights reserved.
#

BUILD_STYLE=configure
BUILD_BITS=64
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=         automake
COMPONENT_VERSION=      1.11.6
COMPONENT_REVISION=     1
COMPONENT_SRC=          $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=      $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
	sha256:53dbf1945401c43f4ce19c1971baecdbf8bc32e0f37fa3f49fe7b6992d0d2030
COMPONENT_ARCHIVE_URL=  http://ftp.gnu.org/pub/gnu/automake/$(COMPONENT_ARCHIVE)

include $(WS_MAKE_RULES)/common.mk

CONFIGURE_OPTIONS  +=	--docdir=$(CONFIGURE_PREFIX)/share/doc/automake-1.11
CONFIGURE_OPTIONS  +=	--infodir=$(CONFIGURE_INFODIR)
CONFIGURE_OPTIONS  +=	PERL="$(PERL)"

# Auto-generated dependencies
PERL_REQUIRED_PACKAGES += runtime/perl
REQUIRED_PACKAGES += shell/ksh93
