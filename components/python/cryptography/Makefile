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
# Copyright (c) 2014, 2018, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2019, Michal Nowak
#

# Component uses ABI3 naming.
PYTHON3_SOABI=abi3

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		cryptography
COMPONENT_VERSION=	2.6.1
COMPONENT_REVISION=	1
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	\
	sha256:26c821cbeb683facb966045e2064303029d572a87ee69ca5a1bf54bf55f93ca6
COMPONENT_ARCHIVE_URL=	$(call pypi_url)
COMPONENT_PROJECT_URL=	https://cryptography.io/

PYTHON_VERSIONS = 2.7 3.4 3.5

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/setup.py.mk
include $(WS_MAKE_RULES)/ips.mk

# 64-bit python loads *.so modules from 64-bit subdir,
# but during tests libraries are installed to non-confirming path
COMPONENT_PREP_ACTION += (cd $(SOURCE_DIR)/src/cryptography/hazmat/bindings &&  $(LN) -sf . 64)

COMPONENT_TEST_DIR=	$(COMPONENT_SRC)
COMPONENT_TEST_CMD=	$(PYTHON) setup.py test
COMPONENT_TEST_ARGS=

build:		$(BUILD_32_and_64)

install:	$(INSTALL_32_and_64)

test:		$(TEST_32_and_64)

REQUIRED_PACKAGES += library/python/pytest-27
REQUIRED_PACKAGES += library/python/pytest-34
REQUIRED_PACKAGES += library/python/pytest-35
REQUIRED_PACKAGES += library/python/cffi
REQUIRED_PACKAGES += runtime/python-34
# Auto-generated dependencies
REQUIRED_PACKAGES += library/security/openssl
REQUIRED_PACKAGES += runtime/python-27
REQUIRED_PACKAGES += runtime/python-35
REQUIRED_PACKAGES += system/library
