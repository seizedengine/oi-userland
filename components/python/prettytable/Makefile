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
# This file was automatically generated using the following command:
#   $WS_TOOLS/python-integrate-project prettytable
#

BUILD_STYLE = pyproject

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME =		prettytable
HUMAN_VERSION =			3.8.0
COMPONENT_SUMMARY =		prettytable - A simple Python library for easily displaying tabular data in a visually appealing ASCII table format
COMPONENT_PROJECT_URL =		https://github.com/jazzband/prettytable
COMPONENT_ARCHIVE_URL =		\
	https://files.pythonhosted.org/packages/18/fa/82e719efc465238383f099c08b5284b974f5002dbe12050bcbbc912366eb/prettytable-3.8.0.tar.gz
COMPONENT_ARCHIVE_HASH =	\
	sha256:031eae6a9102017e8c7c7906460d150b7ed78b20fd1d8c8be4edaf88556c07ce
COMPONENT_LICENSE =		BSD-3-Clause

# prettytable >= 3.8.0 requires Python >= 3.8
PYTHON_VERSIONS := $(filter-out 3.7, $(PYTHON_VERSIONS))

include $(WS_MAKE_RULES)/common.mk

# Remove unpatched version of files from proto area to make sure they do not
# leak into sample manifest.
COMPONENT_POST_INSTALL_ACTION += \
	$(FIND) $(PROTO_DIR)/$(PYTHON_LIB) -name '*.~*~' -exec rm {} \; ;

# Auto-generated dependencies
PYTHON_REQUIRED_PACKAGES += library/python/hatch-vcs
PYTHON_REQUIRED_PACKAGES += library/python/hatchling
PYTHON_REQUIRED_PACKAGES += library/python/wcwidth
PYTHON_REQUIRED_PACKAGES += runtime/python
TEST_REQUIRED_PACKAGES.python += library/python/pytest
TEST_REQUIRED_PACKAGES.python += library/python/pytest-cov
TEST_REQUIRED_PACKAGES.python += library/python/pytest-lazy-fixture
