#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"). You may
# only use this file in accordance with the terms of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source. A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2021 Benjamin S. Osenbach
#

BUILD_STYLE= justmake
include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= chezmoi
COMPONENT_VERSION= 2.34.2
COMPONENT_SUMMARY= Manage your dotfiles across multiple diverse machines, securely.
COMPONENT_PROJECT_URL= https://github.com/twpayne/chezmoi
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_URL= $(COMPONENT_PROJECT_URL)/archive/refs/tags/v$(COMPONENT_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH= sha256:fc47d6e4cbe1b8f4762c204be28e30d9e9f3bcfa8c51ac276cbd1864804b2dc8
COMPONENT_FMRI= application/$(COMPONENT_NAME)
COMPONENT_CLASSIFICATION= Applications/System Utilities
COMPONENT_LICENSE= MIT
COMPONENT_LICENSE_FILE= LICENSE

TEST_TARGET= $(NO_TESTS)
include $(WS_MAKE_RULES)/common.mk

DATE=$(shell date -u +%Y-%m-%d-T%TZ)

COMPONENT_BUILD_ENV += GOOS="illumos"
COMPONENT_BUILD_ENV += GOPATH="$(SOURCE_DIR)/gopath"
COMPONENT_BUILD_ENV += PREFIX=/usr
COMPONENT_BUILD_ENV += VERSION="v$(COMPONENT_VERSION)"
COMPONENT_BUILD_ENV += DATE="'$(DATE)'"
COMPONENT_BUILD_ENV += BUILT_BY="oi-userland"

COMPONENT_INSTALL_ENV += GOOS="illumos"
COMPONENT_INSTALL_ENV += GOPATH="$(SOURCE_DIR)/gopath"
COMPONENT_INSTALL_ENV += PREFIX=/usr
COMPONENT_INSTALL_ENV += VERSION="v$(COMPONENT_VERSION)"
COMPONENT_INSTALL_ENV += DATE="'$(DATE)'"
COMPONENT_INSTALL_ENV += BUILT_BY="oi-userland"

# Go doesn't like symbolic links, so copy the source directory
COMPONENT_COPY_ACTION= ( cp -rL $(SOURCE_DIR)/* $(@D) )

# Upstream Makefile doesn't create PROTO_DIR
COMPONENT_PRE_BUILD_ACTION= ( install -d "$(PROTO_DIR)/usr/bin" )

# Build dependencies
REQUIRED_PACKAGES+=developer/golang
REQUIRED_PACKAGES+=developer/versioning/git

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
