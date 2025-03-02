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
# Copyright 2016 Aurelien Larcher
#

X11_CATEGORY=LIB
BUILD_STYLE= meson
include ../../../make-rules/shared-macros.mk
include $(WS_MAKE_RULES)/x11.mk

COMPONENT_NAME=			libxkbcommon
COMPONENT_VERSION=		1.4.1
COMPONENT_SUMMARY=		xkbcommon - library to handle keyboard descriptions
COMPONENT_PROJECT_URL=	https://xkbcommon.org/
COMPONENT_SRC=			$(COMPONENT_NAME)-xkbcommon-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=		xkbcommon-$(COMPONENT_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH=	sha256:3b86670dd91441708dedc32bc7f684a034232fd4a9bb209f53276c9783e9d40e
COMPONENT_ARCHIVE_URL=	https://github.com/xkbcommon/libxkbcommon/archive/$(COMPONENT_ARCHIVE)
COMPONENT_FMRI=			x11/library/libxkbcommon
COMPONENT_LICENSE_FILE=	LICENSE

TEST_TARGET=	$(TEST_32_and_64)
include $(WS_MAKE_RULES)/common.mk

CONFIGURE_OPTIONS += -Denable-wayland=false
CONFIGURE_ENV += $(COMPONENT_BUILD_ENV)

# for tests
COMPONENT_TEST_TRANSFORMS += '-e "s/[0-9].[0-9][0-9]s//" '
COMPONENT_TEST_TRANSFORMS += \
        '-n ' \
        '-e "/Ok:/p" ' \
        '-e "/Pass:/p" ' \
        '-e "/Fail:/p" ' \
        '-e "/Skipped:/p" ' \
        '-e "/Timeout:/p" '

# Auto-generated dependencies
REQUIRED_PACKAGES += library/libxml2
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += x11/library/libxcb
