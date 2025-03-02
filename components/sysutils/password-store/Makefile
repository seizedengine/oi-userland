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
# Copyright (c) 2021, Andreas Wacknitz
#

BUILD_BITS=				64
BUILD_STYLE=			justmake
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=			password-store
COMPONENT_VERSION=		1.7.4
COMPONENT_REVISION=		1
COMPONENT_SUMMARY=		A password manager
COMPONENT_CLASSIFICATION=Applications/System Utilities
COMPONENT_PROJECT_URL=	https://www.passwordstore.org/
COMPONENT_SRC=			$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=		$(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH=	sha256:cfa9faf659f2ed6b38e7a7c3fb43e177d00edbacc6265e6e32215ff40e3793c0
COMPONENT_ARCHIVE_URL=	https://git.zx2c4.com/password-store/snapshot/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=			utilities/password-store
COMPONENT_LICENSE=		GPLv2

include $(WS_MAKE_RULES)/common.mk

COMPONENT_TEST_TARGETS = test

# Manually added dependencies (according to documentation).
# These are runtime dependencies but we keep them here, too:
REQUIRED_PACKAGES += crypto/gnupg
REQUIRED_PACKAGES += developer/versioning/git
REQUIRED_PACKAGES += file/tree
REQUIRED_PACKAGES += library/libqrencode
REQUIRED_PACKAGES += shell/bash
REQUIRED_PACKAGES += shell/gnu-getopt
REQUIRED_PACKAGES += x11/xclip

# Auto-generated dependencies
REQUIRED_PACKAGES += SUNWcs
