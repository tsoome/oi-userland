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
# Copyright 2016 Jim Klimov
# Copyright 2020 Michal Nowak
#

BUILD_BITS=		32_and_64

include ../../../make-rules/shared-macros.mk

# The primary component delivered here is libmagic.
# There is already the "file" utility with true Unix legacy in our OS,
# still, for the sake of completeness and to match GNU/Linux userland
# we also deliver "gfile" built from darwinsys sources, as a bonus.
COMPONENT_NAME=		file
COMPONENT_FMRI=		library/magic
COMPONENT_VERSION=	5.38
COMPONENT_PROJECT_URL=	http://www.darwinsys.com/file/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH=	sha256:593c2ffc2ab349c5aea0f55fedfe4d681737b6b62376a9b3ad1e77b2cc19fa34
COMPONENT_ARCHIVE_URL=	ftp://ftp.astron.com/pub/file/$(COMPONENT_ARCHIVE)
COMPONENT_SUMMARY=	libmagic for recognizing the type of data contained in a computer file using magic numbers
COMPONENT_CLASSIFICATION=	System/Libraries
COMPONENT_LICENSE_FILE=	COPYING
COMPONENT_LICENSE=	BSD

include $(WS_MAKE_RULES)/common.mk

# Auto-generated dependencies
REQUIRED_PACKAGES += library/zlib
REQUIRED_PACKAGES += SUNWcs
REQUIRED_PACKAGES += system/library
