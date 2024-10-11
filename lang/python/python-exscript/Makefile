#
# Copyright (C) 2024 TDT AG <development@tdt.de>
#
# This is free software, licensed under the GNU General Public License v2.
# See https://www.gnu.org/licenses/gpl-2.0.txt for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-exscript
PKG_VERSION:=2.6
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/knipknap/exscript.git
PKG_SOURCE_VERSION:=v2.6
PKG_MIRROR_HASH:=e76dc120806036aa7916b199cb9742acfc0c91d1a2af21afab7377a1342b1c07

PKG_MAINTAINER:=Lukas Voegl <lvoegl@tdt.de>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING

PYTHON3_PKG_WHEEL_NAME:=Exscript
PYTHON3_PKG_WHEEL_VERSION:=DEVELOPMENT

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-exscript
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Exscript
  URL:=https://github.com/knipknap/exscript
  DEPENDS:= \
    +python3 \
    +python3-paramiko \
    +python3-cryptodomex
endef

define Package/python3-exscript/description
  Exscript is a Python module and a template processor for automating network
  connections over protocols such as Telnet or SSH. We attempt to create the
  best possible set of tools for working with Telnet and SSH.
endef

$(eval $(call Py3Package,python3-exscript))
$(eval $(call BuildPackage,python3-exscript))
$(eval $(call BuildPackage,python3-exscript-src))
