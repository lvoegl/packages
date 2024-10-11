#
# Copyright (C) 2024 TDT AG <development@tdt.de>
#
# This is free software, licensed under the GNU General Public License v2.
# See https://www.gnu.org/licenses/gpl-2.0.txt for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=edl
PKG_VERSION:=3.62
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bkerler/edl.git
PKG_SOURCE_VERSION:=d2c585e4ccc066895b71ca9014c1ebb5af316e07
PKG_MIRROR_HASH:=1a52a0b2cd5f89719b105a562e4601ca1024b052d658be9260c480861a18d763

PKG_MAINTAINER:=Lukas Voegl <lvoegl@tdt.de>
PKG_LICENSE:=GPL-3.0-or-later
PKG_LICENSE_FILES:=LICENSE

PYTHON3_PKG_WHEEL_NAME:=edlclient

include $(INCLUDE_DIR)/package.mk
include ../../lang/python/python3-package.mk

define Package/edl
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Qualcomm EDL
  URL:=https://github.com/bkerler/edl
  DEPENDS:= \
    +python3 \
    +python3-pyserial \
    +python3-colorama \
    +python3-cryptodome \
    +python3-lxml \
    +python3-docopt \
    +python3-passlib \
    +python3-requests \
    +python3-exscript \
    +python3-pyusb
endef

define Package/edl/description
  Inofficial Qualcomm Firehose / Sahara / Streaming / Diag Tools
endef

define Build/Configure
	$(call Build/Configure/Default)
	$(RM) $(PKG_BUILD_DIR)/pyproject.toml
endef

define Py3Build/Install
	$(call Py3Build/Install/Default)
	$(SED) '1s|^#!.*/python3.*|#!/usr/bin/env python3|' \
		$(PKG_INSTALL_DIR)/usr/bin/*
endef

define Py3Package/edl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/usr/lib/python3.11/site-packages
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION)/site-packages/$(PYTHON3_PKG_WHEEL_NAME) \
		$(1)/usr/lib/python$(PYTHON3_VERSION)/site-packages/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/python$(PYTHON3_VERSION)/site-packages/$(PYTHON3_PKG_WHEEL_NAME)-$(PKG_VERSION).dist-info \
		$(1)/usr/lib/python$(PYTHON3_VERSION)/site-packages/
endef

$(eval $(call Py3Package,edl))
$(eval $(call BuildPackage,edl))
$(eval $(call BuildPackage,edl-src))
