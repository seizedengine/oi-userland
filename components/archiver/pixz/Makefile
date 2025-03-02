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
# Copyright (c) 2012, 2013, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2016, Jim Klimov
# Copyright (c) 2018, Michal Nowak
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=			pixz
COMPONENT_VERSION=		1.0.7
COMPONENT_REVISION=		1
COMPONENT_SUMMARY=		parallel indexing version of XZ
COMPONENT_SRC=			$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_PROJECT_URL=	https://github.com/vasi/$(COMPONENT_NAME)/
COMPONENT_ARCHIVE=		$(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH=	sha256:e5e32c6eb0bf112b98e74a5da8fb63b9f2cae71800f599d97ce540e150c8ddc5
COMPONENT_ARCHIVE_URL=	$(COMPONENT_PROJECT_URL)/releases/download/v$(COMPONENT_VERSION)/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=			compress/pixz
COMPONENT_CLASSIFICATION=	Applications/System Utilities
COMPONENT_LICENSE=		BSD-like
COMPONENT_LICENSE_FILE=	LICENSE

include $(WS_MAKE_RULES)/common.mk

CFLAGS += $(CPP_LARGEFILES)

PKG_PROTO_DIRS += $(BUILD_DIR_64)
PKG_PROTO_DIRS += $(COMPONENT_DIR)/files

# Userland default includes -mt which links with libthread which we don't need.
studio_MT =

COMPONENT_PREP_ACTION = (cd $(SOURCE_DIR) && $(AUTORECONF) -if)

CONFIGURE_OPTIONS += --with-libiconv-prefix=$(CONFIGURE_PREFIX)

ASLR_MODE = $(ASLR_ENABLE)

# Build dependencies added manually
REQUIRED_PACKAGES += text/asciidoc

# Note: We have one failing test because we don't have cppcheck.

# Auto-generated dependencies
REQUIRED_PACKAGES += compress/xz
REQUIRED_PACKAGES += library/libarchive
REQUIRED_PACKAGES += system/library
